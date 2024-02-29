<template>
  <div>
    <q-card flat bordered>
      <q-card-section>
        <q-item>
          <q-item-section>
            <q-item-label class="text-h6">Reporting Manager</q-item-label>
            <q-item-label caption
              >Immediate manager an employee reports to.</q-item-label
            >
          </q-item-section>
        </q-item>
        <div class="col q-mt-xs">
          <div class="row q-col-gutter-sm">
            <div class="col-md-12 col-xs-12">
              <q-select
                dense
                outlined
                :model-value="reportingManagerModal"
                use-input
                hide-selected
                fill-input
                input-debounce="0"
                :options="reportingManagerOptions"
                label="Choose Staff"
                transition-show="scale"
                transition-hide="scale"
                @filter="filterFn"
                @input-value="setModel"
                ><template v-slot:no-option>
                  <q-item>
                    <q-item-section class="text-grey">
                      No results
                    </q-item-section>
                  </q-item>
                </template>
              </q-select>
            </div>
            <div class="col-md-12 col-xs-12">
              <q-input
                disable
                dense
                clearable
                outlined
                v-model="designationModal"
                type="tel"
                label="Designation"
              />
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const staffOptions = [
  'Subeesh Sudhakaran',
  'Rohan R Nair',
  'Vibin Ashokh',
  'Ossama Alla',
  'Sudheesh Sudhakaran',
  'Ibjaz Thambi',
];
const reportingManagerModal = ref(null);
const reportingManagerOptions = ref(staffOptions);
const designationModal = ref('Fleet Manager');

const filterFn = (val, update) => {
  update(() => {
    const needle = val.toLowerCase();
    reportingManagerOptions.value = staffOptions.filter((v) =>
      v.toLowerCase().includes(needle)
    );
  });
};
const setModel = (val) => {
  reportingManagerModal.value = val;
};
</script>
