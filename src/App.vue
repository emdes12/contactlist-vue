<script setup>
import { ref } from "vue";
import Header from "./components/Header.vue";
import AddContact from "./components/AddContact.vue";
import ContactList from "./components/ContactList.vue";
import Individual from "./components/Individual.vue";

const contacts = [
  {
    name: "Mrs. Gabrielle Quigley",
    nickname: "Kitty",
    phonenumber: "(123) 456-7890",
    email: "kitty@example.com",
  },
  {
    name: "Ms. Theo Ward",
    nickname: "Tiger",
    phonenumber: "(987) 654-3210",
    email: "tiger@example.com",
  },
  {
    name: "Dr. Winston Fisher",
    nickname: "Whale",
    phonenumber: "(555) 123-4567",
    email: "whale@example.com",
  },
  {
    name: "Miss Leslie Glover",
    nickname: "Lion",
    phonenumber: "(888) 777-5555",
    email: "lion@example.com",
  },
  {
    name: "Mr. Amara Franco",
    nickname: "Penguin",
    phonenumber: "(111) 222-3333",
    email: "penguin@example.com",
  },
  {
    name: "Mrs. Teddy Luna",
    nickname: "Elephant",
    phonenumber: "(999) 888-7777",
    email: "elephant@example.com",
  },
  {
    name: "Dr. Jazmine Doyle",
    nickname: "Giraffe",
    phonenumber: "(444) 555-6666",
    email: "giraffe@example.com",
  },
  {
    name: "Ms. Brayan Wilkerson",
    nickname: "Kangaroo",
    phonenumber: "(777) 666-9999",
    email: "kangaroo@example.com",
  },
  {
    name: "Mr. Trinity Madden",
    nickname: "Bear",
    phonenumber: "(333) 444-5555",
    email: "bear@example.com",
  },
  {
    name: "Miss Valeria Rhodes",
    nickname: "Dolphin",
    phonenumber: "(222) 333-4444",
    email: "dolphin@example.com",
  },
  {
    name: "Mrs. Shyla Bradford",
    nickname: "Monkey",
    phonenumber: "(666) 777-8888",
    email: "monkey@example.com",
  },
  {
    name: "Dr. Soren Melton",
    nickname: "Zebra",
    phonenumber: "(444) 333-2222",
    email: "zebra@example.com",
  },
  {
    name: "Ms. Riley Carr",
    nickname: "Turtle",
    phonenumber: "(777) 999-6666",
    email: "turtle@example.com",
  },
  {
    name: "Mr. Talia Vargas",
    nickname: "Koala",
    phonenumber: "(555) 888-7777",
    email: "koala@example.com",
  },
  {
    name: "Miss Devyn Mcgee",
    nickname: "Ostrich",
    phonenumber: "(111) 999-4444",
    email: "ostrich@example.com",
  },
  {
    name: "Mrs. Ashlynn Gallagher",
    nickname: "Panda",
    phonenumber: "(666) 555-2222",
    email: "panda@example.com",
  },
  {
    name: "Dr. Zack Booth",
    nickname: "Horse",
    phonenumber: "(888) 333-6666",
    email: "horse@example.com",
  },
  {
    name: "Mr. Guadalupe George",
    nickname: "Koala",
    phonenumber: "(999) 444-5555",
    email: "koala@example.com",
  },
  {
    name: "Miss Lincoln Scott",
    nickname: "Duck",
    phonenumber: "(222) 444-5555",
    email: "duck@example.com",
  },
];

let isNewContact = ref(false);
let isContactList = ref(true);

// handle show AddContact Form
const showNewContact = () => {
  isNewContact.value = !isNewContact.value;
  isContactList.value = !isContactList.value;
  console.log(isNewContact);
};

//  handle show individual contact - ShowContact
let individualContact;
let idvContact = ref(false);

const showIdvContact = (id) => {
  console.log(`the user to show is ${id}`);
  individualContact = contacts.filter((contact) => contact.name === id
  )
  console.log(individualContact)

  if (id = false) {
    idvContact.value = !idvContact.value;
  isContactList.value = !isContactList.value;
  }
  idvContact.value = !idvContact.value;
  isContactList.value = !isContactList.value;
};
</script>

<template>
  <Header @showForm="showNewContact" />
  <main
    class="container mx-auto border flex items-center w-[400px] md:w-[600px] justify-center p-3 w-fit gap-4 flex-col"
  >
    <!-- add Contact form -->
    <AddContact v-show="isNewContact" />

    <Individual :individualContact="individualContact" v-show="idvContact" @backToContacts="console.log(showIdvContact())"/>

    <!-- contact list -->
    <ContactList
      @contactShow="showIdvContact"
      v-show="isContactList"
      :contacts="contacts"
    />
  </main>
</template>

<style scoped></style>
