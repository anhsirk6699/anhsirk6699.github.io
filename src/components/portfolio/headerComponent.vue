<template>
    <header class="header">
        <nav class="navbar-header">
            <div class="logo">A</div>
            <div class="nav-items" style="padding-right: 50px;">
                <ol>
                    <li style="transition-delay: 100ms;"> <a href="#about">About</a></li>
                    <li style="transition-delay: 200ms;"> <a href="#experience">Experience</a></li>
                    <li style="transition-delay: 300ms;"> <a href="#work">Work</a></li>
                    <li style="transition-delay: 400ms;"> <a href="#contact">Contact</a></li>
                </ol>
                <div style="transition-delay: 400ms;">
                    <a class="resume-button" href="../../assets/resume.pdf" target="_blank" rel="noopener noreferrer">Resume</a>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'headerComponent'
}
</script>

<style lang="scss">
@import '../../assets/styles/headerStyle.scss'; 
@import '../../assets/styles/variables';
</style>