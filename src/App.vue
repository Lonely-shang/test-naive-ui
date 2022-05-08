


<template>
  <div style="width: 150px">
    <n-select
      :options="options"
      :reset-menu-on-options-change="false"
      @scroll="handleScroll"
    />
  </div>
</template>

<script setup lang="ts">
  import { ref } from "vue";

  const options = ref([
      {
        label: 'Drive My Car',
        value: 'song1'
      },
      {
        label: 'Norwegian Wood',
        value: 'song2'
      },
      {
        label: "You Won't See",
        value: 'song3'
      },
      {
        label: 'Nowhere Man',
        value: 'song4'
      },
      {
        label: 'Think For Yourseld',
        value: 'song5'
      },
      {
        label: 'The Word',
        value: 'song6'
      },
      {
        label: 'Michelle',
        value: 'song7'
      },
      {
        label: 'What goes on',
        value: 'song8'
      },
      {
        label: 'Girl',
        value: 'song9'
      },
      {
        label: "I'm looking through you",
        value: 'song10'
      },
      {
        label: 'In My Life',
        value: 'song11'
      },
      {
        label: 'Wait',
        value: 'song12'
      }
    ]);

  function handleScroll (e: Event) {
    console.log(e);
    const currentTarget = e.currentTarget as HTMLElement
    if (
      currentTarget.scrollTop + currentTarget.offsetHeight >=
      currentTarget.scrollHeight
    ) {
      options.value.push(
        {
          label: `v1-${options.value.length}`,
          value: `v1-${options.value.length}`
        },
        {
          label: `v2-${options.value.length}`,
          value: `v2-${options.value.length}`
        }
      )
    }
  }

</script>

<style>

</style>
