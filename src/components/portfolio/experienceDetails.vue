<template>
  <section class="experience" id="experience">
    <h2 class="numbered-heading">Where I’ve Worked</h2>
    <div class="inner">
      <!-- Tabs -->
      <div role="tablist" class="tab-list" aria-label="Job tabs">
        <button
          v-for="(experience, index) in experiences"
          :key="index"
          role="tab"
          :tabindex="activeTab === index ? 0 : -1"
          :aria-selected="activeTab === index"
          :aria-controls="'panel-' + index"
          @click="setActiveTab(index)"
          :class="activeTab === index ? 'tab-button-active' : 'tab-button'">
          {{ experience.buttonName }}
        </button>
      </div>

      <!-- Tab Panels -->
      <div class="tab-content">
        <div
          v-for="(experience, index) in experiences"
          :key="'panel-' + index"
          role="tabpanel"
          :id="'panel-' + index"
          :aria-labelledby="'tab-' + index"
          :aria-hidden="activeTab !== index"
          v-show="activeTab === index"
          class="tab-panel-body"
        >
          <h3>
            <span>{{ experience.position }}</span>
            <span class="company-name">&nbsp;@&nbsp;{{ experience.company }}</span>
          </h3>
          <p class="range">{{ experience.range }}</p>
          <ul v-if="experience.responsibilities.length">
            <li v-for="(responsibility, i) in experience.responsibilities" :key="i">
              {{ responsibility }}
            </li>
          </ul>
          <p v-else>No responsibilities listed.</p>
        </div>
      </div>
    </div>
  </section>
</template>


<script>
export default {
  name: 'experienceDetails',
  data() {
    return {
      activeTab: 0,
      experiences: [
        {
          buttonName: "L2 Software Dev",
          position: "L2 Software Engineer",
          company: "Linways",
          range: "Nov 2021 - Present",
          responsibilities: [
            "Led team in developing a new pitch module, ensuring seamless integration",
            "Conceptualized and delivered a Vue.js project within 2 months, emphasizing plug-and-play functionality.",
            "Implemented two additional modules with an integrated payment gateway.",
            "Leveraged AWS for scalability, reliability, and security.",
            "Established coding standards and style guide for organizational efficiency.",
            "Optimized complex queries for improved database performance.",
            "Led development of upgraded module versions for successful outcomes."
          ],
        },
        {
          buttonName: "L1 Software Dev",
          position: "L1 Software Engineer",
          company: "Linways",
          range: "Jul 2020 - Nov 2021",
          responsibilities: [
            "Optimized critical web applications, improving performance by 70% through code refactoring and stream lining manual tasks.",
            "Led design of modern and trended Vue UI, enhancing user experience and engagement.",
            "Collaborated closely with senior developers to ensure adherence to coding standards.",
            "Promptly resolved software defects, contributing to project success and stakeholder satisfaction."
          ],
        },
        {
          buttonName: "Embeded Dev",
          position: "Embeded Developer",
          company: "Presevi Industries",
          range: "Jun 2016 - Jul 2017",
          responsibilities: [
            "Streamlined coding, testing, and implementation of C programs for embedded projects, resulting in a 20% reduction in development time and a 15% increase in system efficiency."
          ],
        },
      ],
    };
  },
  methods: {
    setActiveTab(index) {
      this.activeTab = index;
    },
  },
};
</script>

<style lang="scss">
@import '../../assets/styles/mainPage.scss'; 
@import '../../assets/styles/variables';
</style>