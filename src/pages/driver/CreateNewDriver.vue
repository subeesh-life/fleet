<template>
  <div>
    <CreateNewHeader title="Hi, Let's Create a New Driver" />
    <div class="q-pa-md">
      <q-stepper
        v-model="DriverCreation"
        ref="stepper"
        alternative-labels
        color="primary"
        header-nav
        flat
        animated
        transition-next="slide-down"
        keep-alive
        vertical
      >
        <q-step
          :name="1"
          title="Basic Details"
          icon="settings"
          :done="DriverCreation > 1"
        >
          <div class="row">
            <!-- LabourDesignation -->
            <div class="col">
              <LabourDesignation />
            </div>
          </div>
          <!-- EmpoymentType & DrivingLicense -->
          <div class="row q-mt-xs q-col-gutter-md">
            <div class="col-md-3 col-xs-12">
              <EmpoymentType />
            </div>
            <div class="col">
              <DrivingLicense />
            </div>
          </div>
          <!-- MaritalStatus & EmergencyContact & ReportingManager -->
          <div class="row q-mt-xs q-col-gutter-md">
            <div class="col-md-4 col-xs-12">
              <MaritalStatus />
            </div>
            <div class="col-md-4 col-xs-12">
              <EmergencyContact />
            </div>
            <div class="col-md-4 col-xs-12">
              <ReportingManager />
            </div>
          </div>
        </q-step>
        <q-step
          :name="2"
          title="Profile Details"
          icon="create_new_folder"
          :done="DriverCreation > 2"
        >
          <ProfileDetails />
        </q-step>

        <q-step
          :name="3"
          title="Benefits & Salary"
          icon="add_comment"
          :done="DriverCreation > 3"
        >
          Try out different ad text to see what brings in the most customers,
          and learn how to enhance your ads using features like ad extensions.
          If you run into any problems with your ads, find out how to tell if
          they're running and how to resolve approval issues.
        </q-step>

        <q-step :name="4" title="Documents & Permissions" icon="add_comment">
          Try out different ad text to see what brings in the most customers,
          and learn how to enhance your ads using features like ad extensions.
          If you run into any problems with your ads, find out how to tell if
          they're running and how to resolve approval issues.
        </q-step>

        <template v-slot:navigation>
          <q-stepper-navigation>
            <q-btn
              @click="$refs.stepper.next()"
              color="primary"
              :label="DriverCreation === 4 ? 'Finish' : 'Continue'"
            />
            <q-btn
              v-if="DriverCreation > 1"
              flat
              color="primary"
              @click="$refs.stepper.previous()"
              label="Back"
              class="q-ml-sm"
            />
          </q-stepper-navigation>
        </template>
      </q-stepper>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import CreateNewHeader from 'src/components/global/creation/CreateNewHeader.vue';
import LabourDesignation from 'src/components/widgets/creation/LabourDesignation.vue';
import EmpoymentType from 'src/components/widgets/creation/EmpoymentType.vue';
import DrivingLicense from 'src/components/widgets/creation/DrivingLicense.vue';
import MaritalStatus from 'src/components/widgets/creation/MaritalStatus.vue';
import EmergencyContact from 'src/components/widgets/creation/EmergencyContact.vue';
import ReportingManager from 'src/components/widgets/creation/ReportingManager.vue';
import ProfileDetails from 'src/components/widgets/creation/ProfileDetails.vue';

const DriverCreation = ref(1);
</script>
<style scoped></style>
