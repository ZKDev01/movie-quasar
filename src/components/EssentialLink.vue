<template>
  <q-item
    clickable
    tag="a"
    @click="navegateToLink"
  >
    <q-item-section
      v-if="icon"
      avatar
    >
      <q-icon :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
      <q-item-label caption>
        {{ caption }}
      </q-item-label>
    </q-item-section>
  </q-item>
</template>


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'EssentialLink',
  props: {
    title: {
      type: String,
      required: true
    },
    caption: {
      type: String,
      default: ''
    },
    link: {
      type: String,
      default: '#'
    },
    icon: {
      type: String,
      default: ''
    }
  },
  setup(props){

    const navegateToLink = () => {
      if (props.link.startsWith('http')) {
        window.open(props.link, '_blank')
      } else {
        const link = '#/' + props.link
        window.open(link, '_self')
      }
    }

    return {
      navegateToLink
    }
  }
});
</script>
