<template>
  <q-page class="row items-center justify-evenly">
    <example-component title="Example component" active :todos="todos" :meta="meta"></example-component>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/ExampleComponent.vue';

import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'PageIndex-Movies',
  components: { ExampleComponent },
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'movies1'
      },
      {
        id: 2,
        content: 'movies2'
      },
      {
        id: 3,
        content: 'movies3'
      },
      {
        id: 4,
        content: 'movies4'
      },
      {
        id: 5,
        content: 'movies5'
      }
    ]);
    const meta = ref<Meta>({
      totalCount: 1200
    });
    return { todos, meta };
  }
});

</script>
