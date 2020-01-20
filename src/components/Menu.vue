<template>
  <v-simple-table>
    <template v-slot:default>
      <tbody>
        <tr
          v-for="item in menuItems"
          :key="item.name"
          :class="item.highlight ? 'highlight' : ''"
        >
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
      menuItems: [
        {
          name: "Apple",
          price: 20
        },
        {
          name: "Orange",
          price: 21
        },
        {
          name: "Pear",
          price: 22
        },
        {
          name: "Grape",
          price: 23
        }
      ]
    };
  },
  created() {
    var self = this;
    self.menuItems.map((x, i) => {
      self.$set(self.menuItems[i], "highlight", false);
    });
    var init = 0;
    setInterval(function() {
      if (init === self.menuItems.length) {
        init = 0;
      }
      self.menuItems[init].highlight = true;
      if (init === 0) {
        self.menuItems[self.menuItems.length - 1].highlight = false;
      } else {
        self.menuItems[init - 1].highlight = false;
      }
      init++;
    }, 2000);
  }
};
</script>

<style scoped>
.highlight {
  background-color: grey;
  font-weight: 900;
}
</style>
