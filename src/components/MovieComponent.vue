<template>
  <div>

  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
//import { Movie } from './models';

export default defineComponent({
  name: 'MovieComponent',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup(props) {
    //...
    const f = () => {
      console.log(props)
    }
    f()
  },
});

</script>
