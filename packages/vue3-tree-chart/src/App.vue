<template>
  <div>
    <h1>Vue3</h1>

    <button @click="onChangeDataset">change dataset</button>

    <vue-tree
      style="width: 1440px; height: 950px; border: 1px solid gray"
      :dataset="PCEmployeesData"
      :config="treeConfig"
    />
  </div>
</template>

<script>
import VueTree from "./vue-tree/VueTree.vue";

export default {
  components: { VueTree },
  data() {
    return {
      showTree: false,
      PCEmployeesData: {
        title: "CEO",
        value: "Byron Nicolaides",
        children: [
          { title: "BG,  Marketing and Product", children: [{ title: "Business Development" }, { title: "Digital Experience" } ] },
          { title: "EPMBAO", children: [ { title: "Business Analysis" }, { title: "EPMO" } ]},
          { title: "Group Finance", children: [ { title: "Accounting and Finance", children: [ { title: "Accounting and Finance", children: [ { title: "Finance Director", value: "Andrikopoulos, Konstantinos" }, { title: "Finance Controller", value: "Kontos, Charalampos" }, { title: "Head of Finance", value: "Vasilakos, Konstantinos" }, { title: "Accounting and Finance Manager", value: "Tsapara, Sofia" } ] }] } ]}
        ]
      },
      sampleData: {
        value: "1",
        children: [
          { value: "2", children: [{ value: "4" }, { value: "5" }] },
          { value: "3" },
        ],
      },
      treeConfig: { nodeWidth: 120, nodeHeight: 80, levelHeight: 200 },
    };
  },
  methods: {
    onChangeDataset() {
      this.PCEmployeesData = {
        value: "100",
        children: [
          { value: "200" },
          { value: "300", children: [{ value: "400" }, { value: "500" }] },
        ],
      };
    },
    onClick() {
      this.showTree = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
