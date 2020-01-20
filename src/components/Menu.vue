<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Name</th>
          <th class="text-left">Price</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in desserts" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.price }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
export default {
  data() {
    return {
      menuItems: {
        1: {
          name: "Apple",
          price: 20
        },
        2: {
          name: "Orange",
          price: 21
        },
        3: {
          name: "Pear",
          price: 22
        },
        4: {
          name: "Grape",
          price: 23
        }
      }
    };
  }
};
</script>
