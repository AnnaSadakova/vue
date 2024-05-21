<template>
  <div class="v-cart">
    <h1>Cart</h1>
    <vCartItem
      v-for="item in cart_data"
      :key="item.article"
      :cart_item_data="item"
      @deleteFromCart="deleteFromCart" />
  </div>
</template>

<script>
import vCartItem from "./v-cart-item.vue";
import { mapActions, mapGetters } from "vuex";
export default {
  name: "v-cart",
  components: {
    vCartItem,
  },
  props: {
    cart_data: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {};
  },
  computed: { ...mapGetters(["CART"]) },
  methods: {
    ...mapActions(["DELETE_FROM_CART"]),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index);
    },
  },
};
</script>

<style scoped>
.v-cart {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  color: gray;
  font-size: 20px;
  margin-bottom: 26px;
}
p {
  text-align: center;
  font-size: 20px;
}
</style>
