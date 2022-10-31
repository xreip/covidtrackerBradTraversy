<script setup></script>

<template>
   <header
      class="container flex justify-between items-center  p-4 mb-10 rounded-xl"
   >
      <div class="text-xl md:text-3xl font-thin text-center">VUE SANDBOX</div>
      <nav class="flex p-4">
         <router-link to="/" class="p-4 bg-emerald-300/90 rounded m-1"
            >Home</router-link
         >
         <router-link to="/about" class="p-4 bg-emerald-300/90 rounded m-1"
            >About</router-link
         >
         <router-link to="/counter" class="p-4 bg-emerald-300/90 rounded m-1"
            >Counter</router-link
         >
      </nav>
   </header>
</template>
