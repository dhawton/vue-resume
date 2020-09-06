<template>
  <v-card color="gray" light>
    <v-card-text>
      <Title title="About" />
      <p class="pa-0 mb-0">
        {{ content.about.body }}
      </p>
      <Title title="Experience" />
      <div v-for="(job, key) in content.experience" :key="key">
        <v-card outlined>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="boldjobtitle"
                >{{ job.company }} - <i>{{ job.title }}</i></v-list-item-title
              >
              <v-list-item-subtitle>{{ job.dates.from }} - {{ job.dates.to }}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <p class="pl-7" v-for="(duty, key) in job.duties" :key="key">
            {{ duty }}
          </p>
        </v-card>
      </div>
      <Title title="Certifications" />
      <List icon="mdi-school-outline" :data="content.certifications" />
      <Title title="Education" />
      <List icon="mdi-school" :data="transformedEducation" />
    </v-card-text>
  </v-card>
</template>

<script>
import Title from './Title';
import List from './List';

export default {
  name: 'Content',
  components: {
    Title,
    List,
  },
  props: {
    content: {
      default: () => ({
        about: '',
        experience: [],
        certifications: [],
        education: [],
      }),
    },
  },
  computed: {
    transformedEducation() {
      const edu = [];
      this.content.education.forEach((e) => {
        edu.push({
          title: `${e.school} - ${e.program}`,
          subtitle: `${e.dates.from} - ${e.dates.to}`,
        });
      });
      return edu;
    },
  },
};
</script>

<style scoped>
.boldjobtitle {
  font-weight: bold;
}
</style>
