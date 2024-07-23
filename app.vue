<template>
  <div class="relative  max-w-[288px]">
    <div class="w-full h-full bg-white rounded-lg  overflow-hidden">
      <div class="relative ">
        <div class="absolute top-[40%] z-10 flex justify-between w-full px-14 -translate-y-1/2 ">
          <button @click="prevSlide" class="text-white p-2 rounded-full">&lt;</button>
          <button @click="nextSlide" class="text-white p-2 rounded-full">&gt;</button>
        </div>
        <div class="flex transition-transform duration-300 ease-in-out"
             :style="{ transform: `translateX(-${currentSlide * 90}%)` }">
          <div v-for="(slide, index) in slides" :key="index" class="w-[90%] flex-shrink-0 p-4 relative">

            <div class="bg-red-400 rounded-lg overflow-hidden">
              <img :src="slide.image" :alt="slide.title" class="w-full h-48 object-cover rounded-t-lg"
                   :class="{ 'shadow-lg': (index - currentSlide + slides.length) % slides.length === 1 }">
              <div class="p-4">
                <h3 class="text-xl font-semibold mb-2">{{ slide.title }}</h3>
                <p class="text-gray-600">{{ slide.description }}</p>
              </div>
            </div>


          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
import {ref} from 'vue'

const slides = [
  {title: 'Slide 1', description: 'Description for slide 1', image: 'https://picsum.photos/id/1018/800/600'},
  {title: 'Slide 2', description: 'Description for slide 2', image: 'https://picsum.photos/id/1015/800/600'},
  {title: 'Slide 3', description: 'Description for slide 3', image: 'https://picsum.photos/id/1019/800/600'},
]

const currentSlide = ref(0)

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + slides.length) % slides.length
}
</script>