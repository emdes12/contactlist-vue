<script setup>
const props = defineProps(["contacts"]);
const emits = defineEmits(['contactShow'])

const getInitials = (name) => {
  if (!name) return "";

  const initials = name
    .split(" ")
    .map((word) => word[0])
    .join("")
    .slice(1);

  return initials.toUpperCase();
};

const showContact = (id) => {
  emits('contactShow', id)
  console.log(id)
}
</script>

<template>
  <div class="w-full">
    <h1 class="text-[1.8rem] text-center leading-[50px] font-bold">
      Contact List
    </h1>
    <ul class="w-full">
      <li
        class="flex gap-3 cursor-pointer justify-start items-center border p-3"
        v-for="(contact, index) in contacts"
        :key="index"
        @click="showContact(contact.name)"
      >
        <div
          class="rounded-full flex justify-center items-center w-9 h-9 text-white bg-red-700"
        >
          {{ getInitials(contact.name) }}
        </div>
        <div class="flex flex-col">
          <h3>{{ contact.name }}</h3>
          <p class="text-gray-300 font-light">{{ contact.phonenumber }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
