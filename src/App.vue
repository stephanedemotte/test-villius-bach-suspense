<template>
  <Suspense>
    <HelloWorld />
  </Suspense>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { useClient, fetch } from 'villus'
import { batch } from '@villus/batch'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    useClient({
      url: "https://pet-library.moonhighway.com/",
      use: [batch({ timeout: 1000 })]
    });
  },
}
</script>
