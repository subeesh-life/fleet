<template>
  <div>
    <q-card flat bordered>
      <q-card-section>
        <div class="row items-center q-col-gutter-md">
          <!-- Greater Than MD -->
          <div class="col-md-2 col-xs-12 flex justify-center">
            <q-btn flat>
              <q-avatar rounded size="96px" color="primary" text-color="white">
                JS</q-avatar
              ><q-badge floating color="green">
                Upload
                <q-icon name="image" color="white" class="q-ml-xs" /> </q-badge
            ></q-btn>
          </div>
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="prefixDetails"
              type="text"
              label="Enter Prefix"
              suffix="-GT89378"
              ><template v-slot:before>
                <q-icon name="alternate_email" /> </template
            ></q-input>
          </div>
          <div class="col-md-6 col-xs-12">
            <div class="row flex items-center">
              <div class="col-3 text-right q-px-sm gt-xs text-grey-8">
                <label>Choose Gender</label>
              </div>
              <div class="col">
                <q-btn-toggle
                  class="border"
                  unelevated
                  rounded
                  push
                  glossy
                  v-model="genderModel"
                  spread
                  toggle-color="primary"
                  :options="genderOptions"
                />
              </div>
            </div>
          </div>
        </div>

        <div class="row q-mt-lg q-col-gutter-md">
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="firstnameModal"
              type="text"
              label="First Name"
              ><template v-slot:before> <q-icon name="person" /> </template
            ></q-input>
          </div>
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="lastnameModal"
              type="text"
              label="Last Name"
              ><template v-slot:before> <q-icon name="person" /> </template
            ></q-input>
          </div>
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              v-model="birthdateModal"
              label="Date of Birth"
              ><template v-slot:before> <q-icon name="cake" /> </template>
              <template v-slot:append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy
                    cover
                    transition-show="scale"
                    transition-hide="scale"
                  >
                    <q-date v-model="birthdateModal">
                      <div class="row items-center justify-end">
                        <q-btn
                          v-close-popup
                          label="Close"
                          color="primary"
                          flat
                        />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </div>
        </div>
        <div class="row q-mt-lg q-col-gutter-md">
          <div class="col-md-4 col-xs-12">
            <q-select
              dense
              outlined
              :model-value="countryModal"
              use-input
              hide-selected
              fill-input
              input-debounce="0"
              :options="countryOptions"
              label="Choose Country"
              transition-show="scale"
              transition-hide="scale"
              @filter="filterFn"
              @input-value="setModel"
              ><template v-slot:before> <q-icon name="public" /> </template>
              <template v-slot:no-option>
                <q-item>
                  <q-item-section class="text-grey">
                    No results
                  </q-item-section>
                </q-item>
              </template></q-select
            >
          </div>

          <div class="col-md-6 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="locationModal"
              type="text"
              label="Select Address"
              ><template v-slot:before> <q-icon name="location_on" /> </template
            ></q-input>
          </div>
          <div class="col-md-2 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="unitModal"
              type="text"
              label="Unit No"
              ><template v-slot:before> <q-icon name="numbers" /> </template
            ></q-input>
          </div>
        </div>
        <div class="row q-mt-lg q-col-gutter-md">
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="emailModal"
              type="email"
              label="Email Address"
              ><template v-slot:before> <q-icon name="email" /> </template>
              <template v-slot:append>
                <q-btn round dense flat icon="add" /> </template
            ></q-input>
          </div>
          <div class="col-md-4 col-xs-12">
            <q-input
              dense
              outlined
              clearable
              v-model="phoneModal"
              type="tel"
              mask="(###) ## - #######"
              label="Contact No"
              ><template v-slot:before> <q-icon name="phone" /> </template>
              <template v-slot:append>
                <q-btn round dense flat icon="add" /> </template
            ></q-input>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const prefixDetails = ref(null);
const genderModel = ref('male');
const genderOptions = [
  { label: 'Male', value: 'male' },
  { label: 'Female', value: 'female' },
];
const firstnameModal = ref(null);
const lastnameModal = ref(null);
const birthdateModal = ref(null);
const countryOptionsList = [
  'United Arab Emirates - AE',
  'India - IN',
  'United States - US',
  'China - CN',
  'Japan - JP',
  'Germany - DE',
  'United Kingdom - GB',
  'France - FR',
  'Italy - IT',
  'Canada - CA',
  'Australia - AU',
  'Russia - RU',
  'Brazil - BR',
  'South Korea - KR',
  'Spain - ES',
  'Mexico - MX',
  'Indonesia - ID',
  'Turkey - TR',
  'Saudi Arabia - SA',
  'South Africa - ZA',
];
const countryModal = ref(null);
const countryOptions = ref(countryOptionsList);
const locationModal = ref(null);
const unitModal = ref(null);
const emailModal = ref(null);
const phoneModal = ref(null);

const filterFn = (val, update) => {
  update(() => {
    const needle = val.toLowerCase();
    countryOptions.value = countryOptionsList.filter((v) =>
      v.toLowerCase().includes(needle)
    );
  });
};
const setModel = (val) => {
  countryModal.value = val;
};
</script>
