<template>
  <div class="article intro__article">
    <div class="article__inner">
      <a href="#" class="article__price">
        <div class="article__price-before">
          от
        </div>
        <div class="article__price-num">{{ priceFormat }} ₽</div>
        <div class="article__price-after">
          в сутки
        </div>
      </a>
      <div class="article__text">
        {{ text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    price: null,
    text: String
  },
  computed: {
    priceFormat: function() {
      let priceFormat = this.price.replace(/\s/g, "");
      priceFormat =
        priceFormat.length > 3
          ? priceFormat.substr(0, priceFormat.length - 3) +
            " " +
            priceFormat.substr(priceFormat.length - 3)
          : priceFormat;
      return priceFormat;
    }
  }
};
</script>

<style scoped lang="sass">
@import "../assets/sass/variables"

.article
  text-align: left
  padding: 5px 0 5px 54px
  position: relative
  &::before
    position: absolute
    left: 0
    top: 0
    content: ""
    height: 100%
    width: 26px
    background-image: url(../assets/frame.png)
    background-position: center
    background-size: 100% 100%
    background-repeat: no-repeat
  &__inner
    display: flex
    align-items: flex-start
    flex-direction: column
  &__price
    color: $creamy-d
    font-family: $montserrat
    font-weight: 500
    margin-bottom: 25px
    @media screen and (max-width: 1440px)
      margin-bottom: 10px
  &__price-before
    font-size: 20px
  &__price-num
    font-size: 43.75px
    line-height: 1em
  &__price-after
    font-size: 18px
    text-align: right

  &__text
    width: 360px
    font-family: $montserrat
    font-weight: 500
    font-size: 17.8px
    line-height: 1.6
    @media screen and (max-width: 1440px)
      width: 100%
      font-size: 16px
</style>
