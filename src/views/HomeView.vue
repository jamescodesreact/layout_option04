<template>
  <div style="height: calc(100vh - 90px)">
    <Splitter
      :style="{ height: '100%', minHeight: '100%' }"
      :panes="horizontalPanes"
      :orientation="'horizontal'"
      @change="onHorizontalChange"
    >
      <template v-slot:left>
        <div class="pane-content">
          <h3>Left pane</h3>
          <p>Resizable. Minimum width of 5%.</p>
        </div>
      </template>
      <template v-slot:center>
        <div class="pane-content">
          <h3>Center pane</h3>
          <p>Resizable only.</p>
        </div>
      </template>
      <template v-slot:right>
        <div class="pane-content">
          <h3>Right pane</h3>
          <p>Resizable.</p>
        </div>
      </template>
    </Splitter>
  </div>
</template>

<script lang="js">
import { defineComponent } from "vue";
import { Splitter } from "@progress/kendo-vue-layout";

export default defineComponent({
  name: "HomeView",
  components: {
    Splitter,
  },
  data() {
    return {
      horizontalPanes: [
        { size: "350px", min: "350px", content: "left" },
        { content: "center" },
        { size: "20%", content: "right" },
      ],
    };
  },
  methods: {
    onHorizontalChange(event) {
      this.horizontalPanes = event.newState;
    },
  },
});
</script>

<style lang="css">
.main-content-container {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
  min-height: 100%;
  padding: 0px;
  margin: 0px;
}
</style>
