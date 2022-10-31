<template>
   <div class=" container grid md:grid-cols-2 gap-4">
      <!-- BOX 1 -->
      <div class="shadow-md bg-violet-400 p-10 text-center rounded">
         <h3 class="text-3xl text-violet-900 font-bold mb-4">Cases</h3>

         <div class="text-2xl mb-4">
            <span class="font-bold">New :</span>
            {{ stats.NewConfirmed }}
         </div>

         <div class="text-2xl mb-4">
            <span class="font-bold">Total :</span>
            {{ stats.TotalConfirmed }}
         </div>
      </div>
      <!-- BOX 2 -->
      <div class="shadow-md bg-violet-400 p-10 text-center rounded">
         <h3 class="text-3xl text-violet-900 font-bold mb-4">F</h3>

         <div class="text-2xl mb-4">
            <span class="font-bold">New :</span>
            {{ stats.NewDeaths }}
         </div>

         <div class="text-2xl mb-4">
            <span class="font-bold">Total :</span>
            {{ stats.TotalDeaths }}
         </div>
      </div>
   </div>
</template>

<script>
export default {
   name: "DataBoxes",
   props: ["stats"],
};
</script>
