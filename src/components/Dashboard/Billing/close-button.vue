<template>
  <button :class="parentClass">
    <redo-icon v-if="parentClass === 'close-modal1'" />
    <div v-else>
      <span class="close-line close-line1"></span>
      <span class="close-line close-line2"></span>
    </div>
  </button>
</template>

<script>
import redoIcon from "./icons/redo-icon";

export default {
  name: "close-button",
  components: {
    redoIcon
  },
  props: {
    parentClass: {
      type: String,
      required: true
    }
  },
  setup(props) {
    console.log(props.parentClass)
  }
}
</script>

<style scoped>
.close-line {
  display: block;
  width: 35px;
  height: 1px;
  border-radius: 5px;
  background-color: #000;
}

.close-line1 {
  transform: rotate(45deg);
}

.close-line2 {
  position: relative;
  top: -1px;
  transform: rotate(-45deg);
}
</style>
