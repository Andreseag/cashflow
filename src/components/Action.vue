<template>
  <button @click="showModal = true">
    Agregar movimiento
  </button>
  <teleport to="#app">
    <Modal v-show="showModal" @close="showModal = false">
      <form @submit.prevent="submit">
        <div class="field">
          <label for="title">Título</label>
          <input id="title" type="text" v-model="title">
        </div>
        <div class="field">
          <label for="amount">Monto</label>
          <input id="amount" type="number" v-model="amount">
        </div>
        <div class="field">
          <label for="description">Descripción</label>
          <textarea rows="4" name="description" id="description" v-model="description"></textarea>
        </div>
        <div class="field">
          <label for="radio-label">
            <input type="radio" name="movementType" value="Ingreso" v-model="movementType">
            <span>Ingreso</span>
          </label>
          <label for="radio-label">
            <input type="radio" name="movementType" value="Gasto" v-model="movementType">
            <span>Gasto</span>
          </label>
        </div>
        <div class="action">
          <button>
            Agregar movimiento
          </button>
        </div>
      </form>
    </Modal>    
  </teleport>
</template>

<script setup>
// components imports
import Modal from "@/components/Modal.vue";

import { ref } from 'vue';

const showModal = ref(false);
const title = ref('');
const amount = ref(0);
const description = ref('');
const movementType = ref('Ingreso');


const submit = () => {
  showModal.value = !showModal.value;
}

</script>

<style scoped>
button {
  color: white;
  font-size: 1.25rem;
  background-color: var(--brand-blue);
  border: none;
  width: 100%;
  padding: 24px 60px;
  border-radius: 60px;
  box-sizing: border-box;
}

form {
  font-size: 1.24rem;
  width: 100%;
}

form .action {
  padding: 0 24px;
}

.field {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  padding: 16px 24px;
}

label {
  margin-bottom: 8px;
}

input,
textarea {
  font-size: 1.24rem;
  border: 2px solid var(--brand-blue);
  border-radius: 8px;
  padding: 8px;
}

input[type="number"] {
  text-align: right;
}

.radio-label {
  display: flex;
  align-items: center;
  margin-top: 8px;
}

.radio-label span {
  margin-top: 4px;
  margin-left: 8px;
}

input[type="radio"] {
  appearance: none;
  width: 1.24rem;
  height: 1.24rem;
  color: var(--brand-blue);
  border: 2px solid var(--brand-blue);
  border-radius: 50%;
}

input[type="radio"]:checked {
  background-color: var(--brand-blue);
}
</style>