<template>
  <Toast></Toast>
  <div class="container">
    <span class="p-float-label p-input-filled" style="margin-right: 1rem">
      <InputText id="txt" type="text" v-model="text" />
      <label for="txt">Text</label>
    </span>
    <Button label="Greet" @click="greet" icon="pi pi-user"></Button>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useToast } from "primevue/usetoast";

const text = ref();
const toast = useToast();
const greet = () => {
  toast.add({
    severity: "success",
    summary: "PrimeTime",
    detail: text.value,
  });
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
</style>
