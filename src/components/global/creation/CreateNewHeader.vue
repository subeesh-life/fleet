<template>
  <div class="row no-wrap">
    <q-toolbar>
      <loard-icons-widget :iconUrl="icons.DRIVER" :size="40"></loard-icons-widget>
      <q-toolbar-title class="text-weight-medium">{{ title }}</q-toolbar-title>
      <div class="q-pa-md q-gutter-sm">
        <loard-icons-widget :iconUrl="icons.CLOSE" :size="40"></loard-icons-widget>
      </div>
    </q-toolbar>
  </div>
  <q-separator />
</template>

<script>
import { defineComponent } from 'vue';
import LoardIconsWidget from 'src/components/widgets/icons/LoardIconsWidget.vue'
import LOARDICONS from 'src/assets/constants/LoardiconConstants.js';

export default defineComponent({
  props: {
    title: String,
    iconUrl: String,
    size: Number,
  },
  components: {
    LoardIconsWidget
  },
  setup() {
    return {
      icons: LOARDICONS,
    };
  },
});
</script>

<style scoped></style>
