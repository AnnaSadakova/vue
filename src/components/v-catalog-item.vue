<template>
  <div class="v-catalog-item">
    <img
      class="v-catalog-item-image"
      :src="'../public/images/' + product_data.image"
      alt="pic" />
    <p class="v-catalog-item-name">{{ product_data.name }}</p>
    <p class="v-catalog-item-price">{{ product_data.price }}</p>
    <button class="v-catalog-item-add_to_card_btn" @click="SendDataToParent()">
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
    SendDataToParent() {
      this.$emit("addToCart", this.product_data.article);
    },
    }
};
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 grey;
  padding: 20px;
  margin: 20%;
  &__img {
    max-width: 100px;
  }
}
</style>
