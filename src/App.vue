<template>
  <div>
    <div class="mainContent">
      <div class="leftBar">
        <searchbarComponent />
        <tableComponent :columns="table.columns" :rows="table.rows" />
      </div>
      <div class="rightBar">
        <showClientComponent :clientData="client" />
      </div>
      <tableComponent :columns="table.columns" :rows="table.rows" />
      <br />
      <showClientComponent :clientData="client" />
      <br />
      <carnetValidityComponent :clientHasMembership="active" />
      <br />
      <buttonComponent label="kliknij mnie" />
      <br />
      <br />
      <searchbarComponent />
      <br />
      <spinnerComponent />
    </div>
    <sidebarComponent />
  </div>
</template>

<script>
import buttonComponent from "./components/button/buttonComponent.vue";
import tableComponent from "./components/table/tableComponent.vue";
import showClientComponent from "./components/showClientComponent/showClientComponent.vue";
import carnetValidityComponent from "./components/carnetValidityComponent.vue/carnetValidityComponent.vue";
import searchbarComponent from "./components/searchbarComponent/searchbarComponent.vue";
import spinnerComponent from "./components/spinnerComponent/spinnerComponent.vue";
import sidebarComponent from "./components/sidebarComponent/sidebarComponent.vue";

export default {
  /* eslint-disable */
  name: "App",
  components: {
    buttonComponent,
    tableComponent,
    showClientComponent,
    carnetValidityComponent,
    searchbarComponent,
    spinnerComponent,
    sidebarComponent,
  },
  data() {
    return {
      table: {
        columns: ["Imię", "Nazwisko", "Telefon", "Email"],
        rows: [
          {
            Imię: "Alice",
            Nazwisko: "Nowak",
            Telefon: "560229123",
            Email: "email@213.pl",
          },
          {
            Imię: "Bob",
            Nazwisko: "Beksiński",
            Telefon: "560229124",
            Email: "email@214.pl",
          },
          {
            Imię: "Charlie",
            Nazwisko: "Zawada",
            Telefon: "560229126",
            Email: "email@211.pl",
          },
          {
            Imię: "Eve",
            Nazwisko: "Glik",
            Telefon: "560229121",
            Email: "email@215.pl",
          },
        ],
      },
      client: {
        firstName: "John",
        lastName: "Doe",
        phone: "123-456-7890",
        email: "johndoe@example.com",
        comment: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        membership: "Gold",
        purchaseDate: "2022-01-01",
        validUntil: "2022-12-31",
      },
      active: false,
    };
  },
  methods: {
    change() {
      this.active = !this.active;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
.mainContent {
  margin-left: 50px;
}

.leftBar {
  width: 49%;
  padding-right: 2%;
  display: inline-block;
  vertical-align: top;
}

.rightBar {
  width: 49%;
  display: inline-block;
}
</style>
