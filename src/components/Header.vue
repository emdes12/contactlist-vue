<script setup>
// import {defineProps, defineEmits } from 'vue'
const props = defineProps(['isNewContact']);
const emits = defineEmits(["showForm"]);



const showForm = () => {
  emits("showForm");
  console.log('btn clicked')
};
</script>

<template>
  <header class="container mx-auto px-5 flex justify-between p-3">
    <h1>
      <p class="inline font-black">Contacts</p>
      <p class="italic inline">Book</p>
    </h1>
    <button
      @click="showForm"
      class="titlecase text-white bg-green-600 py-3 px-4 rounded-xl"
    >
      Add contact
    </button>
  </header>
</template>

<style scoped>
h1 {
  font-size: 1.6rem;
  top: -10px;
}
/* 
h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
} */
</style>
