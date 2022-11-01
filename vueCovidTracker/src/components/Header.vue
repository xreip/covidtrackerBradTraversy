<script setup></script>

<template>
   <header
      class="sticky top-0 z-40 bg-[#18181820] flex justify-around items-center px-12 mb-10 backdrop-blur-sm border-b border-stone-400 rounded-xl"
   >
      <div class="text-xl md:text-3xl font-thin text-center">VUE SANDBOX</div>
      <nav class="flex p-4">
         <router-link to="/" class="p-2 hover:bg-emerald-300 rounded m-1 transition duration-300 ease-in-out hover:text-black hover:scale-105  "
            >Home</router-link
         >
         <router-link to="/about" class="p-2 hover:bg-emerald-300 rounded m-1 transition duration-300 hover:text-black hover:scale-105"
            >About</router-link
         >
         <router-link to="/counter" class="p-2 hover:bg-emerald-300 rounded m-1 transition duration-300 hover:text-black hover:scale-105"
            >Counter</router-link
         >
      </nav>
   </header>
</template>
