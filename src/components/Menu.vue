<template>
  <div>
    <table v-for="item in menuItems" :key="item.name">
      {{
        item.name
      }}
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuItems: {
        1: {
          name: "Apple"
        },
        2: {
          name: "Orange"
        },
        3: {
          name: "Pear"
        },
        4: {
          name: "Grape"
        }
      }
    };
  }
};
</script>
