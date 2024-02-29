<template>
  <q-card class="my-card" flat bordered>
    <q-item dense class="bg-indigo-1">
      <q-item-section avatar>
        <q-avatar>
          <lord-icon
            trigger="loop"
            src="https://cdn.lordicon.com/ocqzmzvc.json"
          ></lord-icon>
        </q-avatar>
      </q-item-section>

      <q-item-section>
        <q-item-label class="text-subtitle1 text-weight-bold text-primary"
          >Designation</q-item-label
        >
      </q-item-section>
    </q-item>

    <q-separator />

    <q-card-section>
      <div class="row q-col-gutter-md">
        <div class="col-md-3 col-xs-12">
          <q-select
            disable
            dense
            outlined
            v-model="labourTitleModel"
            :options="labourTitleOptions"
            label="Labour Title"
          />
        </div>
        <div class="col-md-3 col-xs-12">
          <q-select
            dense
            outlined
            v-model="labourPositionModel"
            :options="labourPositionOptions"
            label="Labour Position"
            transition-show="scale"
            transition-hide="scale"
          />
        </div>
        <div class="col-md-3 col-xs-12">
          <q-select
            dense
            outlined
            v-model="labourLevelModel"
            :options="labourLevelOptions"
            label="Labour Level"
            transition-show="scale"
            transition-hide="scale"
          />
        </div>
        <div class="col-md-3 col-xs-12">
          <!-- mask="date" :rules="['date']" -->
          <q-input
            dense
            outlined
            v-model="joiningDateModel"
            label="Joining Date"
          >
            <template v-slot:append>
              <q-icon name="event" class="cursor-pointer">
                <q-popup-proxy
                  cover
                  transition-show="scale"
                  transition-hide="scale"
                >
                  <q-date v-model="joiningDateModel">
                    <div class="row items-center justify-end">
                      <q-btn v-close-popup label="Close" color="primary" flat />
                    </div>
                  </q-date>
                </q-popup-proxy>
              </q-icon>
            </template>
          </q-input>
        </div>
      </div>
    </q-card-section>
  </q-card>
</template>
<script setup>
import { ref } from 'vue';
const labourTitleModel = ref(['Driver']);
const labourTitleOptions = ['Driver'];
const labourPositionModel = ref(null);
const labourPositionOptions = ['Senior Driver', 'Junior Driver'];
const labourLevelModel = ref(null);
const labourLevelOptions = [
  'Level - 1',
  'Level - 2',
  'Level - 3',
  'Level - 4',
  'Level - 5',
];
const joiningDateModel = ref(null);
</script>
