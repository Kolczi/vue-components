<template>
  <div class="membership-status" :class="{ active: clientHasMembership }">
    <div class="status-circle" :class="{ active: clientHasMembership }">
      <div class="status-icon">
        <fa icon="fas fa-check" v-if="clientHasMembership" />
        <fa icon="fas fa-times" class="redEx" v-else />
      </div>
    </div>
    <div class="status-label">
      {{
        clientHasMembership
          ? "Posiada aktywny karnet"
          : "Nie posiada aktywnego karnetu"
      }}
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    clientHasMembership: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<style>
.membership-status {
  display: flex;
  align-items: center;
  font-size: 18px;
  border: 1px solid #2ecc71;
  box-shadow: 0px 0px 10px #2ecc71;
  border-radius: 10px;
  padding: 10px;
}

.membership-status {
  border: 1px solid #ff4d4f;
  box-shadow: 0px 0px 10px #ff4d4f;
}

.membership-status.active {
  border: 1px solid #2ecc71;
  box-shadow: 0px 0px 10px #2ecc71;
}

.status-circle {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #ccc;
  margin-right: 10px;
  overflow: hidden;
}

.status-circle.active {
  background-color: #2ecc71;
}

.status-icon {
  color: white;
  font-size: 20px;
  transition: transform 0.2s ease-in-out;
}

.status-label {
  color: #555;
}

.redEx {
  color: #ff4d4f;
}
</style>
