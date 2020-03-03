<template>
  <div class="navigation">
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <a :href="phoneNumber">{{ item }}</a>
      </li>
      <li v-if="phone" class="navigation__phone">
        <a :href="`tel:${phoneNumber}`">{{ phone }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    phone: String,
    items: {
      type: Array,
      default: function() {
        return [];
      }
    }
  },
  computed: {
    phoneNumber: function() {
      let number = this.phone.replace(/[\s,(,),-]/g, "");
      return number;
    }
  }
};
</script>

<style scoped lang="sass">
@import "../assets/sass/variables"

.navigation
  z-index: 10
  // background-color: $green
  display: flex
  justify-content: flex-end
  &__phone
    border: 1px solid $creamy-d
    border-radius: 10px
    padding-right: 5px
  ul
    list-style: none
    display: flex
    align-items: center
    margin: 60px 30px 0 0
  li:not(:last-child)
    margin-right: 85px
  a
    display: flex
    align-items: center
    justify-content: center
    min-width: 80px
    padding: 5px 10px
    font-size: 24px
</style>
