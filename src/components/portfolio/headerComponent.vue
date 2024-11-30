<template>
    <header class="header" :class="{ 'hide-header': isHeaderHidden }">
        <nav class="navbar-header">
            <div @click="scrollToSection('personal-details')" class="logo">A</div>
            <div class="nav-items" style="padding-right: 50px;">
                <ol>
                    <li style="transition-delay: 100ms;"> <a @click="scrollToSection('about')" href="#about">About</a></li>
                    <li style="transition-delay: 200ms;"> <a @click="scrollToSection('experience')" href="#experience">Experience</a></li>
                    <li style="transition-delay: 300ms;"> <a @click="scrollToSection('work')" href="#work">Work</a></li>
                    <li style="transition-delay: 400ms;"> <a @click="scrollToSection('contact')" href="#contact">Contact</a></li>
                </ol>
                <div style="transition-delay: 400ms;">
                    <a class="resume-button" href="/assets/resume.pdf" target="_blank" rel="noopener noreferrer">Resume</a>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'headerComponent',
    data() {
        return {
            lastScrollY: 0, 
            isHeaderHidden: false, 
        };
    },
    methods: {
        scrollToSection(sectionId) {
            const element = document.getElementById(sectionId);
            if (element) {
                window.scrollTo({
                    top: element.offsetTop,
                    behavior: 'smooth'
                });
            }
        },
        checkInitialScroll() {
            const hash = window.location.hash.substring(1); 
            if (hash) {
                this.scrollToSection(hash);
            }
        },
        handleScroll() {
            const currentScrollY = window.scrollY;
            if (currentScrollY > this.lastScrollY && currentScrollY > 100) {
                this.isHeaderHidden = true;
            } else {
                this.isHeaderHidden = false;
            }
            this.lastScrollY = currentScrollY; 
        }
    },
    mounted() {
        this.checkInitialScroll();
        window.addEventListener('scroll', this.handleScroll); 
    },
    beforeUnmount() {
        window.removeEventListener('scroll', this.handleScroll); 
    }
}
</script>

<style lang="scss">
@import '../../assets/styles/headerStyle.scss'; 
@import '../../assets/styles/variables';
</style>