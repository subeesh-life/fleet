<template>
  <div>
    <q-card flat bordered>
      <q-card-section>
        <q-item>
          <q-item-section>
            <q-item-label class="text-h6">Marital Status</q-item-label>
            <q-item-label caption>
              Indicates a person's legal relationship status
            </q-item-label>
          </q-item-section>
        </q-item>
        <!-- <q-separator class="q-mb-sm" /> -->
        <div class="column flex">
          <div class="col">
            <q-radio
              v-model="maritalStatusModal"
              checked-icon="task_alt"
              unchecked-icon="panorama_fish_eye"
              val="single"
              label="Single"
            />
            <q-radio
              v-model="maritalStatusModal"
              checked-icon="task_alt"
              unchecked-icon="panorama_fish_eye"
              val="married"
              label="Married"
            />
            <q-radio
              v-model="maritalStatusModal"
              checked-icon="task_alt"
              unchecked-icon="panorama_fish_eye"
              val="divorced"
              label="Divorced"
            />
          </div>
          <div class="col q-mt-xs">
            <q-select
              dense
              outlined
              v-model="nationalityModel"
              :options="nationalityOptions"
              label="Nationality"
              transition-show="scale"
              transition-hide="scale"
            />
          </div>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>
<script setup>
import { ref } from 'vue';
const maritalStatusModal = ref('single');
const nationalityModel = ref(['United Arab Emirates - AE']);
const nationalityOptions = ['United Arab Emirates - AE', 'India - IN'];
</script>
