<template>
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 mb-10 lg:mb-14">
      <div
        v-for="certificado in certificados"
        :key="certificado.title"
        class="group flex flex-col rounded-xl hover:shadow-md focus:outline-none focus:shadow-md transition"
      >
        <div class="aspect-w-16 aspect-h-9">
          <img 
            :src="certificado.image" 
            :alt="certificado.title"
            class="w-full"
          >
        </div>
        <div class="p-2 md:p-3">
          <p class="mt-2 text-xs uppercase text-gray-600 dark:text-neutral-400">
            {{ certificado.company }} - {{ certificado.date }}
          </p>
          <h5 class="mt-2 text-xg font-medium text-gray-800 group-hover:text-blue-600 dark:text-neutral-300 dark:group-hover:text-white">
            {{ certificado.title }}
          </h5>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CertificadosGrid',
    data() {
      return {
        certificados: [
          {
            date: "2023",
            company: "Coderhouse",
            image: "6489c612dafb840002c19dbe.webp",
            title: "Data Analytics",
            link: ""
          },
          {
            date: "2023",
            company: "Coderhouse",
            image: "6594140fb7e797addec0b3f9.webp",
            title: "Data Science",
            link: ""
          }
        ]
      }
    }
  }
  </script>
