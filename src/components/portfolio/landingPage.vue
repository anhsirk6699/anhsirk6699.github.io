<template>
    <div id="landing-page" :class="{ 'light-mode': isLightMode }">
        <headerComponent></headerComponent>
        <socialMedia></socialMedia>
        <h1>Welcome to My Website</h1>
        <p>This is a simple theme style example.</p>
        <a href="#">This is a link</a>
        <button @click="toggleTheme">Toggle Light/Dark Mode</button>
    </div>
</template>

<script>
import headerComponent from './headerComponent.vue'
import socialMedia from './socialMedia.vue'




export default {
    data() {
        return {
            isLightMode: false
        }
    },
    methods: {
        toggleTheme() {
            this.isLightMode = !this.isLightMode;
        }
    },
    components: {   
        headerComponent,
        socialMedia
    }
}
</script>