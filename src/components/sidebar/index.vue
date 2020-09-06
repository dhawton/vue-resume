<template>
  <v-card color="gray">
    <v-card-text>
      <div class="text-sm-center mb-6 mt-3 sectiontext">
        <h1>Daniel A. Hawton</h1>
        <span>Programmer, Photographer, System Admin</span>
      </div>

      <div v-for="section in ['info', 'social']" :key="section">
        <Section :data="sections[section]" />
      </div>
    </v-card-text>
  </v-card>
</template>

<script>
import Section from './Section';

export default {
  name: 'Sidebar',
  components: {
    Section,
  },
  props: {
    sections: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style scoped>
.sectiontext {
  color: #ffffff;
}
</style>
