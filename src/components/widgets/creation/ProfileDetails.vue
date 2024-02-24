<template>
  <div>
    <q-card flat bordered>
      <q-card-section>
        <div class="row items-center q-col-gutter-md">
          <!-- Greater Than MD -->
          <div class="col-md-2 col-xs-12 gt-sm">
            <q-btn flat>
              <q-avatar rounded size="96px" color="primary" text-color="white">
                JS</q-avatar
              ><q-badge floating color="green">
                Upload
                <q-icon name="image" color="white" class="q-ml-xs" /> </q-badge
            ></q-btn>
          </div>
          <!-- Less Than MD -->
          <div class="col-xs-12 lt-md flex flex-center">
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
              <div class="col-3 text-right q-px-sm gt-xs">
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
                  :options="[
                    { label: 'Male', value: 'male' },
                    { label: 'Female', value: 'female' },
                  ]"
                />
              </div>
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    const prefixDetails = ref('');
    const genderModel = ref('male');

    return {
      prefixDetails,
      genderModel,
    };
  },
});
</script>
