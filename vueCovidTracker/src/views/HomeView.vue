<script setup>
import DataTitle from "../components/DataTitle.vue";
import DataBoxes from "../components/DataBoxes.vue";
import CountrySelect from "../components/CountrySelect.vue";
</script>
<template>
   <main v-if="!loading">
      <DataTitle :text="title" :dataDate="dataDate" />
      <h3
         v-if="!message === ''"
         class="container block bg-red-800 mb-4 rounded p-4 text-center font-black text-xl text-red-500 border border-red-500"
      >
         {{ message }}
      </h3>
      <DataBoxes :stats="stats" />
      <CountrySelect @get-country="getCountryData" :countries="countries" />
      <button
         @click="clearCountryData"
         v-if="stats.Country"
         class="container block bg-green-600 p-3 mt-10 focus:outline-none hover:bg-green-400 rounded w-1/4"
      >
         Clear Country
      </button>
   </main>

   <main v-else class="flex flex-col align-center justify-center text-center">
      <div class="text-gray-500 text-3xl mt-10 mb-6">Fetching Data</div>
      <img :src="loadingImage" class="w-24 m-auto" alt="" />
   </main>
</template>

<script>
export default {
   name: "Home",
   // components: {
   //    DataTitle,
   //    DataBoxes,
   //    CountrySelect
   // PAS L'Impression qu'il faille exporter comme ça mtn ^^

   // },
   data() {
      return {
         loading: true,
         title: "Global",
         dataDate: "",
         stats: {},
         countries: [],
         Message: "",
         loadingImage: new URL("../assets/logo.svg", import.meta.url).href,
      };
   },
   methods: {
      async fetchCovidData() {
         const res = await fetch("https://api.covid19api.com/summary");
         const data = await res.json();
         return data;
      },
      getCountryData(country) {
         this.stats = country;
         this.title = country.Country;
      },
      async clearCountryData() {
         this.loading = true;
         const data = await this.fetchCovidData();
         this.title = "Global";
         this.stats = data.Global;
         this.loading = false;
      },
   },
   async created() {
      const data = await this.fetchCovidData();
      // console.log(data);
      this.dataDate = data.Date;
      this.stats = data.Global;
      this.countries = data.Countries;
      this.loading = false;
      this.message = data.Message;
      // console.log(this.message + "salut")
   },
};
</script>
