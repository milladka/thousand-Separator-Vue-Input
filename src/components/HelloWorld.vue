<template>
  <input type="text" v-model="fValue">
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      value: ""
    };
  },
  computed: {
    fValue: {
      // getter
      get: function() {
        return this.value;
      },
      // setter
      set: function(newValue) {
        // newValue = newValue.replace(".", "");
        // this.value =
        //   newValue.substr(0, newValue.length - 2) +
        //   "." +
        //   newValue.substr(newValue.length - 2);
        this.value = newValue
          .toString()
          .replace(/\,/g, "")
          .replace(/(\d)(?=(\d{3})+(?!\d))/g, "$1,");
        // .replace(",", "")
        // .replace(/\B(?=(\d{3})+(?!\d))/g, ",");

        // add thousend separator formatting here
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
