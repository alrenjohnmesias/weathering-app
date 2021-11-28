<template>
  <div class="wrapper">
    <div id="buttons">
      <div class="md-layout">
          <div
          class="md-layout-item md-size-25 md-xsmall-size-100 md-small-size-50 md-medium-size-25"
        >
          <md-field>
            <md-input v-model="initial" placeholder="Regular"></md-input>
          </md-field>
        </div>
      </div>


    </div>
    <!-- end buttons -->
  
  </div>
</template>

<script>
import { Pagination } from "../../components";
import { Slider } from "../../components";
import { Badge } from "../../components";

export default {
  components: {
    Pagination,
    Slider,
    Badge
  },
  data() {
    return {
      defaultPagination: 3,
      infoPagination: 3,
      initial: null,
      floatingLabel: null,
      success: null,
      error: null,
      withMIcon: null,
      withFaIcon: null,
      checkbox1: true,
      checkbox2: null,
      checkbox3: true,
      checkbox4: null,
      radio1: true,
      radio2: false,
      switch1: true,
      switch2: null,
      amount: 30,
      amount2: 60,
      buffer: 40,
      sliders: {
        simple: 40,
        rangeSlider: [20, 60]
      }
    };
  }
};
</script>

<style lang="scss" scoped>
.vertical-center {
  display: flex;
  align-items: center;
}
.flex-column {
  display: flex;
  flex-direction: column;
}
.md-checkbox,
.md-radio {
  display: flex;
  margin: 0;
  margin-bottom: 0.5rem;
}
</style>
