<script setup>
import { ref } from "vue";

defineProps(["message"]);
const emit = defineEmits(["update:modelValue"]);

const inputMessage = ref("Pass from the child component");

function messageEmitted() {
  if (inputMessage.value.trim() !== "") {
    emit("update:message", inputMessage.value);
    inputMessage.value = "";
  }
}
</script>

<template>
  <div class="border-2 rounded my-10 p-5">
    <h1 class="text-black-900 text-xl font-bold my-5">Child Component:</h1>
    <h2 class="text-black text-xl my-5">
      Message :
      <span class="text-yellow-600 hover:text-yellow-900">{{ message }}</span>
    </h2>

    <input
      type="text"
      class="border-2 rounded p-2"
      v-model="inputMessage"
      placeholder="Enter a message"
    />

    <button
      @click="messageEmitted()"
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold my-8 py-2 px-4 rounded"
    >
      Send
    </button>
  </div>
</template>
