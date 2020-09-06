<template>
  <div>
    <v-list-item v-for="(item, key) in data" :key="key">
      <v-list-item-icon>
        <v-icon>{{ icon }}</v-icon>
      </v-list-item-icon>
      <v-list-item-content>
        <v-list-item-title v-if="typeof item === 'string'">{{ item }}</v-list-item-title>
        <v-list-item-title v-else>{{ item.title }}</v-list-item-title>
        <v-list-item-subtitle v-if="typeof item === 'object' && item.subtitle">{{
          item.subtitle
        }}</v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: {
    data: Array,
    icon: [String, Object],
  },
};
</script>
