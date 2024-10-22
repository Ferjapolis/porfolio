<!-- IconWrapper.vue -->
<template>
    <component :is="svgIcon" v-bind="$attrs" />
</template>

<script>

// Importa tus SVG aquí
import GitHubIcon from '../icons/Github.astro'
import LinkIcon from '../icons/Link.astro'
import HTMLIcon from '../icons/HTML.astro'
import CSSIcon from '../icons/CSS.astro'
import PYTHONIcon from '../icons/Python.astro'
import VuejsIcon from '../icons/Vuejs.astro'
import VuetifyIcon from '../icons/Vuetify.astro'
import PlotlyIcon from '../icons/Plotly.astro'
import RaspberryIcon from '../icons/Raspberry.astro'

const iconMap = {
    GitHub: GitHubIcon,
    Link: LinkIcon,
    HTML: HTMLIcon,
    CSS: CSSIcon,
    PYTHON: PYTHONIcon,
    Vuejs: VuejsIcon,
    Vuetify: VuetifyIcon,
    Plotly: PlotlyIcon,
    Raspberry: RaspberryIcon
}

export default {
    props: {
        name: {
            type: String,
            required: true
        }
    },
    setup(props) {
        return iconMap[props.name] || 'span'
    }
}
</script>