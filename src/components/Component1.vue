<template>
  <div>
    Component1 {{ count }} -- {{ total }}
    Numbers {{ numbers.a }} -- {{ numbers.b }}
    <button @click="onClick">Incrementcount</button>
    <button @click="increase('a')">Increment a</button>
    <button @click="increase('b')">Increment b</button>
  </div>
</template>

<script lang="ts">
import { ref, reactive, computed } from 'vue'

export default {
  props: {
    msg: String,
  },


  setup() {
      const count = ref(11);
      const numbers = reactive({
        a: 0,
        b: 0,
      });
      // const total = computed()
    const total = numbers.a + numbers.b;

      const onClick = () => { count.value++; };
      const increase = (key: string) => { numbers[key]++ };

      return {
        count,
        numbers,
        onClick,
        increase,
      }
    },

    // mounted() {
    //     console.log(this.count) // 0
    // }
}
</script>