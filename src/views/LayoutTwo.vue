<template>
  <button @click="hidePaneLeft = !hidePaneLeft">
    {{ hidePaneLeft ? "Show" : "Hide" }} Left Panel
  </button>
  <button @click="hidePaneRight = !hidePaneRight">
    {{ hidePaneRight ? "Show" : "Hide" }} Right Panel
  </button>
  <splitpanes class="default-theme" style="height: calc(100vh - 111px)">
    <pane v-if="!hidePaneLeft">
      <span>1</span>
    </pane>
    <pane>
      <span>2</span>
    </pane>
    <pane v-if="!hidePaneRight">
      <span>3</span>
    </pane>
  </splitpanes>
</template>

<script lang="js">
import { defineComponent } from "vue";
import { Splitpanes, Pane } from 'splitpanes'
import 'splitpanes/dist/splitpanes.css'

export default defineComponent({
  name: "LayoutTwo",
  components: { Splitpanes, Pane },
  data() {
    return {
      hidePaneLeft: false, // Initially Left Panel is visible
      hidePaneRight: false, // Initially Right Panel is visible
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
