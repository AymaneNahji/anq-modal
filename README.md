# An Quasar Modal

A flexible and customizable modal component built with Vue 3, Quasar, and TypeScript.

## Installation

```bash
npm install anq-modal
```

## Quick Start

```vue
<template>
  <AnModal
    ref="modalRef"
    title="My Modal"
    @okClick="onModalOk"
  >
    <template #content>
      <div>Your content here</div>
    </template>
  </AnModal>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { AnModal } from 'anq-modal';

const modalRef = ref<InstanceType<typeof AnModal> | null>(null);

// Show modal
modalRef.value?.show();

// Hide modal
modalRef.value?.hide();
</script>
```

## Features

- 🎯 Built with Vue 3 and TypeScript
- 🎨 Quasar Framework integration
- 🎭 Customizable slots for content and buttons
- 🔒 Optional persistent mode
- 🎮 Programmatic control
- 🎨 Customizable styling
- 📱 Responsive design

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `title` | `string` | `'Title'` | Modal title |
| `persistent` | `boolean` | `false` | If true, modal can't be closed by clicking outside |
| `hideOkBtn` | `boolean` | `false` | Hide the OK button |
| `hideActions` | `boolean` | `false` | Hide the entire actions section |
| `okLabel` | `string` | `'Ok'` | Label for the OK button |
| `cancelLabel` | `string` | `'Cancel'` | Label for the Cancel button |
| `btnsColor` | `string` | `'primary'` | Color for the buttons |
| `modalCardProps` | `object` | `{}` | Props to pass to the underlying q-card component |

## Events

| Event | Description |
|-------|-------------|
| `okClick` | Emitted when OK button is clicked |
| `hide` | Emitted when modal is hidden |

## Slots

| Slot | Props | Description |
|------|-------|-------------|
| `content` | - | Main content of the modal |
| `close-icon-btn` | `{ color, disable }` | Custom close button |
| `cancel-btn` | `{ color, disable, label }` | Custom cancel button |
| `ok-btn` | `{ click, color, label }` | Custom OK button |

## Methods

| Method | Description |
|--------|-------------|
| `show()` | Show the modal |
| `hide()` | Hide the modal |

## Example with Custom Slots

```vue
<template>
  <AnModal
    ref="modalRef"
    title="Custom Modal"
    :persistent="true"
  >
    <template #content>
      <div class="p-4">
        <p>Custom content here</p>
      </div>
    </template>
    
    <template #close-icon-btn="{ color }">
      <q-btn icon="close" :color="color" round flat v-close-popup />
    </template>
    
    <template #cancel-btn="{ color, label }">
      <q-btn :color="color" :label="label" flat v-close-popup />
    </template>
    
    <template #ok-btn="{ click, color, label }">
      <q-btn :color="color" :label="label" @click="click" />
    </template>
  </AnModal>
</template>
```

## Dependencies

- Vue 3
- Quasar Framework
- TypeScript

## License

MIT

## Author

Aymane Nahji 