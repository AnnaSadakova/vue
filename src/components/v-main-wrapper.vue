<template>
  <div class="v-main-wrapper">
    <vCatalog />
    <vCard />
  </div>
</template>

<script>
import vCatalog from "./v-catalog.vue";
import vCart from "./v-cart.vue";

export default {
  name: "v-main-wrapper",
  components: { vCatalog, vCart },
  props: {},
  data() {
    return {
      title: "Hello World",
    };
  },
  computed: {},
  methods: {},
  watch: {},
  mounted() {
    console.log("Hello");
  },
};
</script>

<style lang="scss">
.v-main-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 900px;
  margin: 0 auto;
  & {
    display: flex;
  }
}
</style>
