<template>
  <div
    class="tooltip-container"
    :class="{
      'tooltip-top': position === 'top',
      'tooltip-right': position === 'right',
      'tooltip-bottom': position === 'bottom',
      'tooltip-left': position === 'left',
    }"
  >
    <slot name="trigger" />
    <div class="tooltip" v-show="show">
      <div class="tooltip-arrow"></div>
      <div class="tooltip-inner">
        <slot name="content" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    position: {
      type: String,
      default: "top",
      validator: (value) => ["top", "right", "bottom", "left"].includes(value),
    },
  },
  data() {
    return {
      show: false,
    };
  },
  methods: {
    showTooltip() {
      this.show = true;
    },
    hideTooltip() {
      this.show = false;
    },
  },
};
</script>

<style>
.tooltip-container {
  position: relative;
}

.tooltip-trigger {
  cursor: pointer;
}

.tooltip {
  position: absolute;
  background-color: #333;
  color: #fff;
  padding: 0.5rem;
  border-radius: 4px;
  font-size: 0.9rem;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.2s, visibility 0.2s;
  z-index: 999;
}

.tooltip.show {
  opacity: 1;
  visibility: visible;
}

.tooltip-top .tooltip-arrow {
  border-bottom-color: #333;
}

.tooltip-right .tooltip-arrow {
  border-left-color: #333;
}

.tooltip-bottom .tooltip-arrow {
  border-top-color: #333;
}

.tooltip-left .tooltip-arrow {
  border-right-color: #333;
}

.tooltip-arrow {
  position: absolute;
  border-style: solid;
  width: 0.5rem;
  height: 0.5rem;
  border-color: transparent;
  border-width: 0.25rem;
}

.tooltip-inner {
  margin-top: 0.25rem;
}

.tooltip-trigger-button {
  background-color: #ddd;
  color: #333;
  padding: 0.5rem;
  border: none;
  border-radius: 4px;
  font-size: 0.9rem;
  cursor: pointer;
}

.tooltip-trigger-button:hover {
  background-color: #ccc;
}
</style>
