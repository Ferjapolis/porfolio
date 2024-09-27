<!-- ProfileCard.vue -->
<template>
  <div class="h-80 bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
    <img class="rounded-t-lg object-cover w-full  h-30 md:h-auto " :src="image" :alt="title" />
    <div class="p-3 h-20">
      <h3 class="mb-2 text-2xs font-bold tracking-tight text-gray-900 dark:text-white">{{ title }}</h3>
      <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ position }}</p>
      <div>
        <IconWrapper v-for="tech in tags" :name="tech" :key="tech"/>
      </div>
      <a :href="github" v-if="github"
        class="inline-flex items-center mr-2 px-2 py-1 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
        <IconWrapper name="GitHub" />
        Repo
      </a>
      <a :href="link" v-if="link"
        class="inline-flex items-center px-2 py-1 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
        Ir
      </a>
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
      required: false
    }
  }
}
</script>