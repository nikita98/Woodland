<template>
  <div class="intro">
    <navigation phone="+7 (495) 005-61-59" :items="array" />

    <div class="intro__title">
      <div class="intro__title-top">
        отель-заповедник
      </div>
      <img class="intro__title-main" src="../assets/forest-text.png" alt="" />
      <div class="intro__title-bot">
        премиальный отдых в подмосковье
      </div>
    </div>
    <my-article
      price="5500 "
      text="4х разовое питание и all inclusive. Собственное подсобное хозяйство, бассейн, баня, конный двор
и контактный зоопарк."
    />
    <availability />
    <img src="../assets/deer.png" alt="deer" class="deer" />
  </div>
</template>

<script>
import navigation from "./navigation.vue";
import myArticle from "./myArticle.vue";
import availability from "./availability.vue";
export default {
  props: {
    msg: String
  },
  components: {
    navigation,
    availability,
    "my-article": myArticle
  },
  data() {
    return {
      array: ["об отеле", "номера и цены", "мероприятия", "контакты"]
    };
  }
};
</script>

<style scoped lang="sass">
@import "../assets/sass/variables"

.intro
  width: 100%
  height: 100vh
  min-height: 100vh
  display: flex
  flex-direction: column
  align-items: flex-end
  background-image: url("../assets/bg.png")
  background-position: center
  background-repeat: no-repeat
  background-size: cover
  position: relative
  &__title
    margin-top: 5vh
    margin-right: 13vw
    @media screen and (max-width: 1440px)
      margin-right: 8vw
      margin-top: 4vh
  &__title-top
    font-size: 34px
    text-align: left
    margin-bottom: 15px
    margin-left: 8.3%
    @media screen and (max-width: 1440px)
      font-size: 24px
  &__title-main
    height: 27vh
    @media screen and (max-width: 1440px)
      height: 20vh
  &__title-bot
    font-size: 50px
    font-style: $book
    text-align: right
    margin-top: 25px
    @media screen and (max-width: 1440px)
      font-size: 32px
  &__availability
    position: absolute
    bottom: 9%
    right: 0
    @media only screen and (max-width : 1224px)
      bottom: 0
  &__article
    margin-top: 8vh
    width: 46%
    @media screen and (max-width: 1440px)
      width: 50%
      margin-top: 3vh
.deer
  position: absolute
  left: 0
  top: 0
  // width: 50%
  height: 1210px
  pointer-events: none
  @media only screen and (max-width : 1224px)
    height: 80%
</style>
