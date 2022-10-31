<template>
   <div class="container block">
      <h1 class="text-5xl font-black text-center mb-4">Vue State counter</h1>

      <p class="text-5xl m-auto text-center">{{ count }}</p>
      <div class="p-2 text-center mt-5 grid grid-cols-2 gap-10">
         <i
            @click="increase"
            class="fa-solid fa-plus p-4 rounded-full bg-gradient-to-tl from-purple-900 to-emerald-400  cursor-pointer"
         ></i>
         <i
            @click="decrease"
            class="fa-solid fa-minus p-4 rounded-full bg-gradient-to-tl from-purple-900 to-emerald-400  cursor-pointer"
         ></i>
      </div>
   </div>
</template>

<script>
import { ref } from "vue";
export default {
   name: "Counter",
   components: {},
   setup() {
      const count = ref(0);

      const increase = () => {
         count.value++;
      };
      const decrease = () => {
         count.value--;
      };
      return { count, increase, decrease };
   },
};
</script>
