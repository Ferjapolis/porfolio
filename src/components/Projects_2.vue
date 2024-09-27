<!-- ProfileGallery.vue -->
<template>
  <div>
    <div class="flex justify-center space-x-4 mb-8">
      <button v-for="category in categories" :key="category" @click="setActiveFilter(category)" :class="[
        'px-4 py-2 rounded-full transition-colors',
        activeFilter === category
          ? 'bg-blue-500 text-white'
          : 'bg-gray-200 text-gray-700 hover:bg-blue-600 hover:text-white'
      ]">
        {{ capitalize(category) }}
      </button>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">

      <ProjectCard v-for="(profile, p) in filteredProfiles" 
      :key="p" 
      :title="profile.name"        
      :position="profile.position" 
      :description="profile.description" 
      :image="profile.image"        
      :github="profile.github" 
      :tags="profile.tags" 
      :link="profile.link" />

    </div>

  </div>
</template>

<script>
import ProjectCard from './ProjectCard.vue'

export default {
  components: {
    ProjectCard
  },
  data() {
    return {
      activeFilter: 'all',
      profiles: [
        {
          name: "Ferreteando - Ordenando tus venta en dos click",
          category: "CRM",
          description: `simplifica la gestión de ventas y presupuestos en ferreterías y pequeños comercios. Permite actualizar precios en tiempo real y generar presupuestos rápidamente. Su interfaz intuitiva y automatización optimizan el flujo de trabajo.`,
          image: "/628_1x_shots_so.webp",
          tags: ["HTML", "CSS", "VUETIFY", "VUE", "PYTHON"],
        },
        {
          name: "PoroIA - ML para el Éxito en el Mundo de League of Legends",
          category: "ML",
          description: `PoroIA analiza partidas clasificatorias de League of Legends en nivel Diamante, centradas en los primeros 10 minutos. Con 10,000 partidas, ofrece información para mejorar rendimiento y estrategias. Es ideal para equipos que buscan optimización.`,
          link: "https://ferjapolis.github.io/Coderhouser-DS-TP0002/Resumen.html",
          github: "https://github.com/Ferjapolis/Coderhouser-DS-TP0002",
          image: "/LoL.webp",
          tags: ["PYTHON", "PLOTLY"],
        },
        {
          name: "Sistema de Vivero Automatizado con Raspberry Pi",
          category: "Sistem Domotic",
          description: `El proyecto automatiza el riego y monitoreo de un vivero con sensores de humedad, temperatura, presión y pH, gestionado desde una web en Flask. Los datos se registran para análisis predictivos que optimizan el cuidado de las plantas.`,
          image: "/342shots_so.webp",
          tags: ["PYTHON", "PLOTLY", "RPIO"],
        },
        {
          name: "Generador de Metadata a partir de tablas exceles",
          category: "ETL",
          description: `El script original se encarga de leer un archivo de Excel de entrada, procesar los datos de los distintos sheets (o "tablas") del archivo y generar un archivo de salida en formato Parquet con información sobre las relaciones de datos entre las tablas.`,
          image: "/logo.png",
          github: "https://github.com/Ferjapolis/Metadata_creator",
          tags: ["PYTHON"],
        },
        // Add more profile objects as needed
      ],
      categories: ["all", "development", "design", "marketing"]
    }
  },
  computed: {
    filteredProfiles() {
      return this.activeFilter === 'all'
        ? this.profiles
        : this.profiles.filter(profile => profile.category === this.activeFilter);
    }
  },
  methods: {
    setActiveFilter(category) {
      this.activeFilter = category;
    },
    capitalize(str) {
      return str.charAt(0).toUpperCase() + str.slice(1);
    }
  }
}
</script>
