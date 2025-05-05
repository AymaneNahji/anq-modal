<template>
  <div class="p-5">
    <q-btn label="Open Modal" color="primary" @click="modalRef?.show()" />
    
    <AnqModal
      ref="modalRef"
      title="Example Modal"
      :persistent="false"
      @okClick="onModalOk"
      @hide="onModalHide"
    >
      <template #content>
        <div class="p-4">
          <p>This is an example modal content.</p>
          <p>You can put any content here!</p>
        </div>
      </template>
    </AnqModal>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { AnqModal } from './index';

const modalRef = ref<InstanceType<typeof AnqModal> | null>(null);

const onModalOk = () => {
  console.log('Modal OK clicked');
  modalRef.value?.hide();
};

const onModalHide = () => {
  console.log('Modal hidden');
};
</script>

<style scoped></style>