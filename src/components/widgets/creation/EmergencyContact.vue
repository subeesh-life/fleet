<template>
  <div>
    <q-card>
      <q-card-section>
        <q-item>
          <q-item-section>
            <q-item-label class="text-h6">Emergency Contact</q-item-label>
            <q-item-label caption>
              A person's designated contact for urgent situations.
            </q-item-label>
          </q-item-section>
        </q-item>
        <q-separator class="q-mb-sm" />
        <div class="column flex">
          <div class="col">
            <q-radio v-model="emergencyContactModal" checked-icon="task_alt" unchecked-icon="panorama_fish_eye"
              val="friendsRelatives" label="Friends / Relatives" />
            <q-radio v-model="emergencyContactModal" checked-icon="task_alt" unchecked-icon="panorama_fish_eye"
              val="married" label="Spouse" />

          </div>
          <div class="col q-mt-xs">
            <div class="row q-col-gutter-sm">
              <div class="col-md-6 col-xs-12">
                <q-input dense outlined clearable v-model="fullNameModal" type="text" label="Full Name" />
              </div>
              <div class="col-md-6 col-xs-12">
                <q-input dense clearable outlined v-model="emergencyNumber" type="tel" mask="(###) ## - #######"
                  label="Telephone Number" />
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
    const emergencyContactModal = ref('friendsRelatives');


    return {
      emergencyContactModal,
      fullNameModal: ref(''),
      emergencyNumber: ref(''),



    };
  },
});
</script>
