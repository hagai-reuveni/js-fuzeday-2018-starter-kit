<template>
  <div class="container">
    <img src="../assets/search.png"/>&nbsp;
    <input class="searchbox" type="search" v-model="searchValue">
  </div>
</template>

<style lang="scss" scoped>
.container {
  margin: 0.2em 0em;
  display: flex;
  min-height: 60px;
  width: 100%;
  background-color: transparent;
  .searchbox {
    width: calc(100% - 2em);
    margin-left: 0.2em;
    display: inline-block;
    min-height: 80%;
    font-size: 1em;
    line-height: 1em;
    padding: 0;
    -webkit-appearance: textfield;
    background-color: transparent;
    border: none;
    border-bottom: 1px solid gold;
    &:focus {
      outline: none;
    }
  }
  img {
    height: 50px;
    margin-top: 9px; 
  }
}
</style>

<script>
export default {
  name: "Search",
  props: {
    value: "",
    onSearch: null
  },
  data: function() {
    return {
      searchValue: ""
    };
  },
  watch: {
    searchValue() {
      this.onSearch && this.onSearch(this.searchValue);
    }
  }
};
</script>
