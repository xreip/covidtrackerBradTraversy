<script setup>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
   <Header />
   <RouterView class="router-view min-h-screen" v-slot="{ Component }">
      <Transition name="page-slide" mode="out-in">
         <component :is="Component" />
      </Transition>
   </RouterView>
   <Footer />
</template>

<style>
.page-opacity-enter-active,
.page-opacity-leave-active {
   transition: 200ms ease all;
}
.page-slide-enter-active,
.page-slide-leave-active {
   transition: 200ms ease all;
}
.page-opacity-enter-from,
.page-opacity-leave-to {
   opacity: 0;
}
.page-slide-enter-from,
.page-slide-leave-to {
   opacity: 0;
   transform: translateY(80px);
}
</style>
