<template>
  <div class="flex flex-col rounded-lg shadow-lg bg-indigo-900">
    <div class="relative group h-44 w-full overflow-hidden rounded-t-lg">
      <!-- Imagen de fondo -->
      <img :src="image" :alt="title"
        class="absolute inset-0 w-full h-full object-cover transition-all duration-300 ease-in-out group-hover:scale-110 group-hover:brightness-50" />

      <!-- Contenido superpuesto -->
      <div class="absolute inset-0 flex flex-col justify-end p-6 bg-gradient-to-t from-black/60 to-transparent">
        <!-- Contenido que aparece con fade-up -->
        <div
          class="transform translate-y-8 opacity-0 transition-all duration-300 group-hover:translate-y-0 group-hover:opacity-100">
          <p class="text-sm text-gray-300 mb-2">{{ position }}</p>
          <p class="text-sm text-gray-300 mb-4">{{ description }}</p>

          <!-- Iconos de tecnologías -->
          <div class="flex flex-wrap gap-2 mb-4">
            <IconWrapper v-for="tech in tags" :name="tech" :key="tech" class="w-6 h-6 text-white" />
          </div>

        </div>
      </div>
    </div>
    <div class="py-3 px-4">
      <!-- Título siempre visible -->
      <h3 class="text-xl font-bold text-white mb-2">{{ title }}</h3>
      <!-- Botones de acción -->
      <div class="flex gap-2">
        <a v-if="github" :href="github"
          class="inline-flex items-center px-3 py-1 text-sm font-medium text-white bg-blue-600 rounded-lg hover:bg-blue-700 transition-colors duration-200">
          <IconWrapper name="GitHub" class="w-4 h-4 mr-1" />
          Repo
        </a>
        <a v-if="link" :href="link"
          class="inline-flex items-center px-3 py-1 text-sm font-medium text-white bg-green-600 rounded-lg hover:bg-green-700 transition-colors duration-200">
          Ir
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import IconWrapper from './IconWrapper.vue'

export default {
  components: {
    IconWrapper
  },
  props: {
    title: {
      type: String,
      required: true
    },
    position: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
    github: {
      type: String,
      required: false
    },
    link: {
      type: String,
      required: false
    },
    tags: {
      type: Array,
      required: false,
      default: () => []
    }
  }
}
</script>