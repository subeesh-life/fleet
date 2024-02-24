<template>
  <div>
    <CreateNewDriver />
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import CreateNewDriver from 'src/pages/driver/CreateNewDriver.vue';

export default defineComponent({
  components: {
    CreateNewDriver
  },
  setup() {
    //
  }
});
</script>
