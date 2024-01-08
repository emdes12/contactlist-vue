<template>
    <div class="flex w-full flex-col justify-center items-center gap-8" v-for="idv in individualContact">
      <div class="flex w-full bg-lime-500 px-4 py-2 text-white">
        <div class="cursor-pointer" @click="goBack">Back</div>
      </div>
      <div
        class="rounded-full w-[90px] flex justify-center items-center text-white text-[2rem] font-bold h-[90px] bg-red-900"
      >
        {{ getInitials(idv.name) }}
      </div>
      <div class="w-full flex flex-col">
        <div class="flex gap-4 border w-full px-3 py-1.5">
          <p class="w-[120px] text-gray-500">Name:</p>
          <b>{{idv.name}}</b>
        </div>
        <div class="flex gap-4 border w-full px-3 py-1.5">
          <p class="w-[120px] text-gray-500">Nickname:</p>
          <b>{{idv.nickname}}</b>
        </div>
        <div class="flex gap-4 border w-full px-3 py-1.5">
          <p class="w-[120px] text-gray-500">Phone Number:</p>
          <b>{{idv.phonenumber}}</b>
        </div>
        <div class="flex gap-4 border w-full px-3 py-1.5">
          <p class="w-[120px] text-gray-500">Email:</p>
          <b>{{idv.email}}</b>
        </div>
      </div>
    </div>
</template>

<script setup>
const props = defineProps({
    individualContact: {
        type: Array
    }
})
const emits = defineEmits(['backToContacts'])


const getInitials = (name) => {
    console.log(name)
  if (!name) return "";

  const initials = name
    .split(" ")
    .map((word) => word[0])
    .join("")
    .slice(1);

  return initials.toUpperCase();
};

const goBack = () => {
    console.log('back btn clicked')
    emits('backToContacts')
}
</script>