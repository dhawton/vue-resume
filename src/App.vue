<template>
  <v-app>
    <v-main>
      <v-fade-transition mode="out-in" type="animation">
        <v-main>
          <v-container fluid fill-height>
            <v-layout align-center justify-center>
              <v-col md="11" sm="12">
                <v-row>
                  <v-col md="4" sm="12">
                    <Sidebar :sections="resume.sections.sidebar" />
                  </v-col>
                  <v-col md="8" sm="12">
                    <Content
                      :content="resume.sections.content"
                      :about="resume.sections.content.about.body"
                      :experience="resume.sections.content.experience"
                    />
                  </v-col>
                </v-row>
              </v-col>
            </v-layout>
          </v-container>
        </v-main>
      </v-fade-transition>
    </v-main>
  </v-app>
</template>

<script>
import Sidebar from './components/sidebar';
import Content from './components/content';
import resumeData from './assets/resume.json';

export default {
  name: 'App',

  components: {
    Sidebar,
    Content,
  },

  data: () => ({
    resume: resumeData,
  }),
};
</script>

<style lang="css">
html,
body {
  background-color: #000000;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='250' height='30' viewBox='0 0 1000 120'%3E%3Cg fill='none' stroke='%23001100' stroke-width='10' %3E%3Cpath d='M-500 75c0 0 125-30 250-30S0 75 0 75s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3Cpath d='M-500 45c0 0 125-30 250-30S0 45 0 45s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3Cpath d='M-500 105c0 0 125-30 250-30S0 105 0 105s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3Cpath d='M-500 15c0 0 125-30 250-30S0 15 0 15s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3Cpath d='M-500-15c0 0 125-30 250-30S0-15 0-15s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3Cpath d='M-500 135c0 0 125-30 250-30S0 135 0 135s125 30 250 30s250-30 250-30s125-30 250-30s250 30 250 30s125 30 250 30s250-30 250-30'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat;
  height: 100%;
  width: 100%;
}
.theme--dark.v-application {
  background: none !important;
}
.sectiontitle {
  border-bottom: 1px solid #000000;
  font-weight: bold;
  line-height: 1.5 !important;
  letter-spacing: 0.3em !important;
  text-transform: uppercase;
}
.sectiontext {
  color: #000000;
}
</style>
