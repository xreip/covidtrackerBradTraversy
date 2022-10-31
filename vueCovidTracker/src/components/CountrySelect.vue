<template>
   <div>
      <select v-model="selected" name="" id="" class="container form-select block w-full border p-3 rounded mt-10">
         <option v-for="country in Countries" :value="country.ID">
            {{country.Country}}
         </option>
      </select>
   </div>
</template>

<script>
export default {
   name: "CountrySelect",
   props: ["Countries"],
   data() {
      return { selected: 0 };
   },
};
</script>
