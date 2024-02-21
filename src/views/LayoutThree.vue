<template>
  <button @click="horizontal = !horizontal">
    Switch to {{ horizontal ? "Vertical" : "Horizontal" }}
  </button>

  <splitpanes
    class="default-theme"
    :horizontal="horizontal"
    :first-splitter="firstSplitter"
    style="height: calc(100vh - 111px)"
  >
    <pane v-for="i in 3" :key="i">
      <span>{{ i }}</span>
    </pane>
  </splitpanes>
</template>

<script lang="js">
import { defineComponent } from "vue";
import { Splitpanes, Pane } from 'splitpanes'
import 'splitpanes/dist/splitpanes.css'

export default defineComponent({
  name: "LayoutThree",
  components: { Splitpanes, Pane },
  data() {
    return {
      horizontal: false,
      firstSplitter: false
    }
  }
})
</script>

<style lang="css">
.splitpanes {
  background-color: #f8f8f8;
}

.splitpanes__splitter {
  background-color: #ccc;
  position: relative;
}
.splitpanes__splitter:before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  transition: opacity 0.4s;
  background-color: rgba(255, 0, 0, 0.3);
  opacity: 0;
  z-index: 1;
}
.splitpanes__splitter:hover:before {
  opacity: 1;
}
.splitpanes--vertical > .splitpanes__splitter:before {
  left: -30px;
  right: -30px;
  height: 100%;
}
.splitpanes--horizontal > .splitpanes__splitter:before {
  top: -30px;
  bottom: -30px;
  width: 100%;
}
</style>
