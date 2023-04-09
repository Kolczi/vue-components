<template>
  <div class="sidebar">
    <ul>
      <v-tooltip text="Ustawienia konta" :location="bottom">
        <template v-slot:activator="{ props }">
          <li v-bind="props">
            <a href="#"><fa icon="fa fa-cog"></fa></a>
          </li>
        </template>
      </v-tooltip>
      <v-tooltip text="Użytkownicy" :location="bottom">
        <template v-slot:activator="{ props }">
          <li v-bind="props">
            <a href="#"><fa icon="fa fa-users"></fa></a>
          </li>
        </template>
      </v-tooltip>
      <v-tooltip text="Karnety" :location="bottom">
        <template v-slot:activator="{ props }">
          <li v-bind="props">
            <a href="#"><fa icon="fa fa-credit-card"></fa></a>
          </li>
        </template>
      </v-tooltip>
      <v-tooltip text="Statystyki" :location="bottom">
        <template v-slot:activator="{ props }">
          <li v-bind="props">
            <a href="#"
              ><fa icon="fa fa-chart-bar" :class="{ active: true }"></fa
            ></a>
          </li>
        </template>
      </v-tooltip>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SidebarComponent",
};
</script>

<style scoped>
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  width: 50px;
  background-color: #222;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

li {
  margin-bottom: 10px;
}

a {
  display: block;
  padding: 10px;
  color: #fff;
  text-align: center;
}

a:hover {
  background-color: #555;
}

.active {
  color: #007bff;
  transform: scale(1.5);
}
</style>
