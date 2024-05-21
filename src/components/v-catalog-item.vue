<template>
  <div class="v-catalog-item">
    <img
      class="v-catalog-item-image"
      :src="'../public/images/' + product_data.image"
      alt="pic" />
    <p class="v-catalog-item-name">{{ product_data.name }}</p>
    <p class="v-catalog-item-price">{{ product_data.price }}</p>
    <button class="v-catalog-item-add_to_card_btn" @click="addToCart">
      add
    </button>
  </div>
</template>

<script>
export default {
  name: "v-catalog-item",
  props: {
    product_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    addToCart() {
      this.$emit("addToCart", this.product_data);
    },
  },
};
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 40%;
  box-shadow: 0 0 8px 0 grey;
  padding: 20px;
  margin: 20px;
}
.v-catalog-item-image {
  width: 150px;
  display: block;
  margin: 0 auto;
}
</style>
