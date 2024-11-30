<template>
    <section class="about_me" data-sr-id="0" id="about">
        <h2 class="numbered-heading">About Me</h2>
        <div class="inner">
            <div class="about-writing">
                <div>
                    <div>
                        <p>Results-driven Full Stack Web Developer with a proven track record of delivering robust web solutions. Proficient in
                            Vue.js, PHP, RESTful API development, MySQL, Apache server administration, Git version control, and AWS deployment.</p>
                        <p>Proficient in developing responsive and scalable web applications, fostering cross-team collaboration for timely delivery of high-quality projects.</p>
                        <p>Demonstrates a deep understanding of web development best practices and a dedication
                            to staying updated with industry trends and emerging technologies.</p>
                        <p>Here are a few technologies I’ve been working with recently:</p>
                    </div>
                </div>
                <ul class="skills-list" >
                    <li style="text-align:left" v-for="skill in skills" :key="skill">{{ skill }}</li>
                </ul>
            </div>
            <div class="about-image">
                <div class="wrapper">
                    <div class="img image-wrapper">
                        <div style="max-width: 500px;display: block;">
                            <img :src="currentImage" alt="My Image" style="max-width: 100%; display: block; position: static;">
                            <div aria-hidden="true" style="opacity: 0;transition: opacity 500ms linear 0s;background-color: rgb(232, 232, 232);position: absolute;inset: 0px;object-fit: cover;"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'aboutMe',
    data () {
        return {
            skills : ['MySQL-8','VueJs','JWT','REST-API','AWS','GIT','Redmine','RabitMQ','lodash',],
            images: [
                require('@/assets/images/me.jpg'),
                require('@/assets/images/me1.jpg'),
                require('@/assets/images/me2.jpg'),
                require('@/assets/images/me3.jpg')
            ],
            currentImage: require('@/assets/images/me3.jpg') 
        }
    },
    mounted() {
        this.changeImage();
    },
    methods: {
        changeImage() {
        setInterval(() => {
            const randomIndex = Math.floor(Math.random() * this.images.length);
            this.currentImage = this.images[randomIndex];
        }, 10000); 
        }
    }
  }
  </script>
  
  <style lang="scss">
  @import '../../assets/styles/mainPage.scss'; 
  @import '../../assets/styles/variables';
  </style>
