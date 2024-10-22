<template>
  <a class="group flex flex-col bg-white border shadow-sm rounded-xl hover:shadow-md focus:outline-none focus:shadow-md transition dark:bg-neutral-900 dark:border-neutral-800"
    href="#">
    <div class="aspect-w-16 aspect-h-9">
      <img class="w-full object-cover rounded-t-xl" :src="image" :alt="title">
    </div>
    <div class="p-2 md:p-3">
      <p class="mt-2 text-xs uppercase text-gray-600 dark:text-neutral-400">
        {{ category }}
      </p>
      <h5
        class="mt-2 text-xg font-medium text-gray-800 group-hover:text-blue-600 dark:text-neutral-300 dark:group-hover:text-white">
        {{ title }}
      </h5>
      <div class="mt-2 flex justify-end">
        <a :href="github" v-if="github">
          <span class="inline-flex items-center gap-x-1.5 py-1.5 px-3 rounded-lg text-xs font-medium bg-blue-100 text-blue-800 dark:bg-blue-800/30 dark:text-blue-500">Repo</span>
        </a>
        <a :href="link" v-if="link">
          <span class="ml-3 inline-flex items-center gap-x-1.5 py-1.5 px-3 rounded-lg text-xs font-medium bg-blue-100 text-blue-800 dark:bg-blue-800/30 dark:text-blue-500">Link</span>
        </a>
      </div>
    </div>
  </a>
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
    category: {
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