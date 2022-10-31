<script setup>
import DataTitle from "../components/DataTitle.vue";
import DataBoxes from "../components/DataBoxes.vue";
import CountrySelect from "../components/CountrySelect.vue";
</script>
<template>
   <main v-if="!loading">
      <DataTitle :text="title" :dataDate="dataDate" />
      <DataBoxes :stats="stats" />
      <CountrySelect :countries="countries"/>
   </main>

   <main class="flex flex-col align-center justify-center text-center" v-else>
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
   // },
   data() {
      return {
         loading: true,
         title: "Global",
         dataDate: "",
         stats: {},
         countries: [],
         loadingImage: new URL("../assets/logo.svg", import.meta.url).href,
      };
   },
   methods: {
      async fetchCovidData() {
         const res = await fetch("https://api.covid19api.com/summary");
         const data = await res.json();
         return data;
      },
   },
   async created() {
      const data = await this.fetchCovidData();
      console.log(data);
      this.dataDate = data.Date;
      this.stats = data.Global;
      this.countries = data.Countries;
      this.loading = false;
   },
};

// PAS L'Impression qu'il faille exporter comme ça mtn ^^
</script>
