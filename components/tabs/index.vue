<template>
  <div class="tabs-wrapper">
    <div class="tabs-header">
      <div
        v-for="tab in tabs"
        :key="tab.id"
        :class="['tabs-header-item', { 'tab-active': tab.selected }]"
      >
        <div @click="changeTabItem(tab)">
          {{ tab.name }}
        </div>
      </div>
    </div>
    <div class="tab-body">
      <div v-for="tab in tabs" :key="tab.id">
        <div v-show="tab.selected">
          <slot :name="tab.step" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "./style.scss";
export default {
  props: {
    tabs: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    changeTabItem(tab) {
      this.$emit("tabChange", tab);
    },
  },
};
</script>

<style>
</style>