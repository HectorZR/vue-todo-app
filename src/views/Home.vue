<template>
  <div class="home">
    <Welcome msg="This is a single TODO App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Welcome from '@/components/Welcome.vue';

export default {
  name: 'home',
  components: {
    Welcome,
  },
};
</script>
