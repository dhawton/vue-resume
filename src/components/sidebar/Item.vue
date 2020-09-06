<template>
  <div>
    <v-container fluid class="pa-0 ma-0 pl-3 itemtext">
      <v-row>
        <v-col sm="1" justify-center
          ><v-icon>{{ data.icon }}</v-icon></v-col
        >
        <v-col sm="11">
          <div>{{ data.name }}</div>
          <p class="pa-0 mb-0">
            <a v-if="data.link === true" :href="data.text" target="_blank" class="darkentext">{{
              data.text
            }}</a>
            <span v-else class="darkentext">{{ data.text }}</span>
          </p>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'SidebarSectionItem',
  props: {
    data: {
      type: Object,
      default: () => ({
        name: '',
        icon: '',
        text: '',
        link: false,
      }),
    },
  },
};
</script>

<style scoped>
.title {
  border-bottom: 1px solid #cccccc;
  font-weight: 300;
  line-height: 1.5 !important;
  letter-spacing: 0.1em !important;
  text-transform: uppercase;
}
a, .darkentext {
  color: rgba(255,255,255,0.3);
}
.itemtext {
  color: #ffffff;
}
</style>
