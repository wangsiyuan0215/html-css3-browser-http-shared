<script setup lang="ts">
import { defineProps } from "vue";

defineProps({
  circle: {
    default: false,
  },
});
</script>

<template>
  <div class="break-all">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse quasi
    praesentium similique odio, blanditiis commodi minima ipsum facere totam
    magnam,
    <img
      src="../assets/images/bg.jpg"
      class="m-4 ml-0 t-20 h-40 float-left rounded-md"
      :class="circle ? 'w-50 h-50 object-cover !rounded-full shape-circle' : ''"
    />
    assumenda inventore qui laudantium iste repellat sunt id corporis provident
    reiciendis vel hic quasi tempora? Sed incidunt aperiam eligendi rem
    recusandae temporibus reiciendis nam accusamus libero illo aliquam officia
    sunt voluptate reprehenderit iure molestias eos, repudiandae eius velit!
  </div>
</template>

<style scoped>
.shape-circle {
  shape-outside: circle(50%);
}
</style>
