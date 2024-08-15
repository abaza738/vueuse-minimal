<script setup lang="ts">
const ref1 = ref<string>('');
const ref2 = ref<number>(0);
const reactiveObj = ref({
  id: 1,
  title: '@vueuse/nuxt'
})

watchImmediate([ref1, ref2, reactiveObj], ([r1, r2, obj]) => {
  r1;   // type: string | number | { id: number; title: string; }
  r2;   // type: string | number | { id: number; title: string; }
  obj;  // type: string | number | { id: number; title: string; }
});

watch([ref1, ref2, reactiveObj], ([r1, r2, obj]) => {
  r1;   // type: string
  r2;   // type: number
  obj;  // type: { id: number; title: string; }
}, { immediate: true })
</script>

<template>
  <h1>Nuxt Minimal Starter</h1>
</template>

<style>
html,
body {
  margin: 0px;
  min-height: 100dvh;
  box-sizing: border-box;
}

#__nuxt {
  height: 100dvh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background-color: hsl(225deg, 15%, 5%);
  color: white;
}
</style>
