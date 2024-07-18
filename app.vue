<template>
  <button @click="isModalOpen=true">open</button>
   <Modal
      v-show="isModalOpen"
      @close-modal="isModalOpen = false"
      title="Enregisterer !"
      message="Vos informations ont été enregistrées avec succès !"
      route="/devis"
      button="List Devis"
      :isOpen="isModalOpen"
    />
</template>

<script setup>
import { ref } from 'vue'
import Modal from "~/component/Modal.vue";

const isModalOpen = ref(true)
</script>