<template>
   <div>
      <select
         @change="onChange()"
         v-model="selected"
         name=""
         id=""
         class="container form-select block w-full border p-3 rounded mt-10 text-black"
      >
         <option value="0">Select Country</option>
         <option v-for="country in countries" :value="country.ID">
            {{ country.Country }}
         </option>
      </select>
      <p class="font-medium text-center mt-4">
         API by
         <a class="text-pink-400" href="https://covid19api.com/"
            ><i class="fa-solid fa-user"></i>Covid19api</a
         >
      </p>
   </div>
</template>

<script>
export default {
   name: "CountrySelect",
   props: ["countries"],
   data() {
      return { selected: 0 };
   },
   methods: {
      //emit event upwards
      onChange() {
         const country = this.countries.find(
            (item) => item.ID === this.selected
         );

         this.$emit("get-country", country);
      },
   },
};
</script>
