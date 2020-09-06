<template>
  <div>
    <div class="sectiontitle mb-2 mt-2 sectiontext">
      {{ data.title }}
    </div>
    <slot v-if="$slots.default" />
    <template v-else-if="$scopedSlots.items">
      <slot name="items" :items="data.items" />
    </template>
    <template v-else-if="$scopedSlots.item">
      <slot v-for="(item) in data.items" name="item" :data="item" />
    </template>
    <template v-else>
      <SectionItem v-for="(item, key) in data.items" :key="key" :data="item" />
    </template>
  </div>
</template>

<script>
import SectionItem from './Item';

export default {
  name: 'SidebarSection',
  components: {
    SectionItem,
  },
  props: {
    data: {
      type: Object,
      default: () => ({
        title: '',
        items: [],
      }),
    },
  },
};
</script>

<style scoped>
.sectiontitle {
  border-bottom: 1px solid #cccccc;
  /*font-weight: 300;*/
  font-weight: bold;
  line-height: 1.5 !important;
  letter-spacing: 0.3em !important;
  text-transform: uppercase;
}
.sectiontext {
  color: #ffffff;
}
</style>
