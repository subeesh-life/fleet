<template>
  <div>
    <q-card>
      <q-card-section>
        <q-item>
          <q-item-section>
            <q-item-label class="text-h6">Reporting Manager</q-item-label>
            <q-item-label caption>
              Immediate manager an employee reports to.
            </q-item-label>
          </q-item-section>
        </q-item>
        <q-separator class="q-mb-sm" />
        <div class="col q-mt-xs">
          <div class="row q-col-gutter-sm">
            <div class="col-md-12 col-xs-12">
              <q-input dense outlined clearable v-model="fullNameModal" type="text" label="Full Name" />
            </div>
            <div class="col-md-12 col-xs-12">
              <q-input disable dense clearable outlined v-model="designationModal" type="tel" label="Designation" />
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
    const emergencyContactModal = ref('friendsRelatives');


    return {
      emergencyContactModal,
      fullNameModal: ref('Subeesh Sudhakaran'),
      designationModal: ref('Fleet Manager')


    };
  },
});
</script>
