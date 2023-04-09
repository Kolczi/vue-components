<template>
  <div class="client-data">
    <table>
      <tbody>
        <tr>
          <td>Imię:</td>
          <td>{{ clientData.firstName }}</td>
        </tr>
        <tr>
          <td>Nazwisko:</td>
          <td>{{ clientData.lastName }}</td>
        </tr>
        <tr>
          <td>Telefon:</td>
          <td>{{ clientData.phone }}</td>
        </tr>
        <tr>
          <td>Email:</td>
          <td>{{ clientData.email }}</td>
        </tr>
        <tr v-if="clientData.comment">
          <td>Komentarz:</td>
          <td>{{ clientData.comment }}</td>
        </tr>
        <tr v-if="clientData.membership">
          <td>Karnet:</td>
          <td>{{ clientData.membership }}</td>
        </tr>
        <tr v-if="clientData.purchaseDate">
          <td>Data zakupu:</td>
          <td>{{ clientData.purchaseDate }}</td>
        </tr>
        <tr v-if="clientData.validUntil">
          <td>Karnet ważny do:</td>
          <td>{{ clientData.validUntil }}</td>
        </tr>
      </tbody>
    </table>
    <carnetValidityComponent :clientHasMembership="true">
    </carnetValidityComponent>
  </div>
</template>

<script>
import carnetValidityComponent from "../carnetValidityComponent.vue/carnetValidityComponent.vue";
export default {
  components: {
    carnetValidityComponent,
  },
  props: {
    clientData: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.client-data {
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
}

table {
  width: 100%;
  border-collapse: collapse;
}

td {
  padding: 10px;
  font-size: 18px;
  text-align: left;
}

td:first-child {
  font-weight: bold;
  color: #555;
  width: 30%;
}

tr {
  border-bottom: 1px solid #ccc;
}

tr:last-child {
  border: none;
}
</style>
