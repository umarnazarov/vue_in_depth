<template>
  <div
    class="container_modal z-1"
    v-if="isVisible"
    @click="$emit('closeModal')"
  >
    <div @click.stop class="max-w-25rem w-full bg-white p-5">
      <slot></slot>
    </div>
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "app-modal",
  props: {
    isVisible: {
      type: Boolean,
      required: true,
      default: false
    },
  },
});
</script>
<style lang="css">
.container_modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(82, 82, 82, 0.511);
  display: flex;
  justify-content: center;
  align-items: center;
}
.content_modal {
  width: 450px;
  background-color: #fff;
  padding: 20px;
}
</style>
