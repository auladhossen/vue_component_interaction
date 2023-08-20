<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const message = ref("Message from parent component");
</script>

<template>
  <div class="border-2 rounded my-10 p-5">
    <h1 class="text-black-900 text-xl font-bold my-5">Parent Component:</h1>
    <h4 class="text-black text-l">Message : {{ message }}</h4>
  </div>

  <ChildComponent v-model:message="message"></ChildComponent>
</template>
