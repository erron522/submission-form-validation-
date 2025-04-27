<script setup>
import DoctorInfo from './components/DoctorInfo.vue'
import Form from './components/Form.vue'
</script>

<template>
  <div class="formContainer">
    <div class="formBox">
      <DoctorInfo />
      <Form />
    </div>
  </div>
</template>

<style>
body {
  background: #f5f4fb;
  font-family: Arial;
}

.formContainer {
  max-width: 1200px;
  margin: 0 auto;
}

.formBox {
  display: grid;
  grid-template-columns: 41% 1fr;
  box-shadow: 1px 2px 2px 2px rgba(102, 102, 102, 0.2);
}
</style>
