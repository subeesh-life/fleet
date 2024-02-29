<template>
  <q-card class="my-card" flat bordered>
    <q-item dense class="bg-indigo-1">
      <q-item-section avatar>
        <q-avatar>
          <lord-icon
            trigger="loop"
            src="https://cdn.lordicon.com/intuwtgy.json"
          ></lord-icon>
        </q-avatar>
      </q-item-section>

      <q-item-section>
        <q-item-label class="text-subtitle1 text-weight-bold text-primary"
          >Driving License Class</q-item-label
        >
      </q-item-section>
    </q-item>

    <q-separator />

    <q-card-section>
      <div class="row q-col-gutter-md">
        <div class="col-md-8 col-xs-12">
          <q-select
            dense
            outlined
            v-model="drivingClassModel"
            multiple
            :options="drivingClassOptions"
            use-chips
            label="Choose Class"
            transition-show="scale"
            transition-hide="scale"
          />
        </div>
        <div class="col-md-4 col-xs-12">
          <q-select
            disable
            dense
            outlined
            v-model="drivingEndorsementModel"
            :options="drivingEndorsementOptions"
            label="License Endorsement"
          />
        </div>
      </div>
    </q-card-section>
  </q-card>
</template>
<script setup>
import { ref } from 'vue';
const drivingClassModel = ref(null);
const drivingClassOptions = [
  'Light Vehicle Driving',
  'Motorcycle Driving',
  'Heavy Truck Driving',
  'Heavy Bus Driving',
  'Light Bus Driving',
  'Heavy Vehicle Driving',
  'Forklift Driving',
];
const drivingEndorsementModel = ref('A');
const drivingEndorsementOptions = [];
</script>
