<template>
  <div class="w-full">
      <h1 class="text-[1.8rem] text-center leading-[50px] font-bold">Add a New Contact</h1>
      <form action="" class="flex gap-3 justify-center flex-wrap flex-col w-full">
        <input
          type="text"
          placeholder="Full Name"
          class="border p-2 font-3 w-full"
        />
        <input
          type="text"
          placeholder="Nick Name"
          class="border p-2 font-3 w-full"
        />
        <input
          type="text"
          placeholder="+225426365324"
          class="border p-2 font-3 w-full"
        />
        <input
          type="email"
          placeholder="mail@mail.com"
          class="border p-2 font-3 w-full"
        />
        <button class="titlecase text-white bg-green-600 py-3 px-4 rounded-xl">
          Add contact
        </button>
      </form>
    </div>
</template>

<script>
import { ref, watch } from 'vue';

const isNewContact = ref(false);

watch(isNewContact, (newVal) => {
  console.log('AddContact visibility:', newVal._value);
});
</script>