<template>
  <Transition
    enter-active-class="transition-opacity duration-500 ease-out"
    leave-active-class="transition-opacity duration-500 ease-in"
    enter-from-class="opacity-0"
    leave-to-class="opacity-0"
  >
    <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-85" @click="$emit('close-modal')">
      <div class="relative bg-white h-[400px] w-[500px] rounded-[20px] p-10 text-center" @click.stop>
        <p>hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh</p>
        <p>hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh</p>
        <p>hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh</p>
      </div>
      <div class="absolute top-[10%] right-4 cursor-pointer" @click="$emit('close-modal')">
        <!-- You can add a close icon here if needed -->
      </div>
    </div>
  </Transition>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  message: {
    type: String,
    required: true
  },
  route: {
    type: String,
    required: true
  },
  button: {
    type: String,
    required: true
  },
  isOpen: {
    type: Boolean,
    required: true
  }
})

defineEmits(['close-modal'])
</script>