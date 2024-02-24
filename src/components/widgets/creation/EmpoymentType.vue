<template>
  <q-card class="my-card" flat bordered>
    <q-item dense class="bg-indigo-1">
      <q-item-section avatar>
        <q-avatar>
          <lord-icon
            trigger="loop"
            src="https://cdn.lordicon.com/ryxjnvir.json"
          ></lord-icon>
        </q-avatar>
      </q-item-section>

      <q-item-section>
        <q-item-label class="text-subtitle1 text-weight-bold text-primary"
          >Employee Type</q-item-label
        >
      </q-item-section>
    </q-item>

    <q-separator />

    <q-card-section>
      <div class="row">
        <div class="col">
          <q-radio
            v-model="employeeTypeModal"
            checked-icon="task_alt"
            unchecked-icon="panorama_fish_eye"
            val="fullTime"
            label="Full Time"
          />
          <q-radio
            v-model="employeeTypeModal"
            checked-icon="task_alt"
            unchecked-icon="panorama_fish_eye"
            val="partTime"
            label="Part Time"
          />
        </div>
      </div>
    </q-card-section>
  </q-card>
</template>
<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const employeeTypeModal = ref('fullTime');
    return {
      employeeTypeModal,
    };
  },
});
</script>
