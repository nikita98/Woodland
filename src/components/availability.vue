<template>
  <div class="availability intro__availability">
    <img
      src="../assets/laces.png"
      alt=""
      class="availability__laces availability__before"
    />
    <form class="availability__inner">
      <div class="availability__title">
        Бронирование номеров
      </div>
      <div class="availability__input-wrap">
        <img
          src="../assets/small-calendar.png"
          alt="calendar"
          class="availability__input-img"
        />
        <div class="availability__input-text">Заезд</div>
        <DatePicker
          name="start"
          :mode="mode"
          v-model="startDate"
          :min-date="new Date()"
          color="green"
        />
      </div>
      <div class="availability__input-wrap">
        <img
          src="../assets/small-calendar.png"
          alt="calendar"
          class="availability__input-img"
        />
        <div class="availability__input-text">Выезд</div>
        <DatePicker
          :mode="mode"
          v-model="endDate"
          :min-date="startDate"
          color="green"
        />
      </div>
      <div class="availability__input-wrap availability__input-wrap_guests">
        <input
          type="number"
          class="availability__guests-input"
          v-model="guests"
          min="1"
          max="99"
        />
        <div class="availability__input-text availability__input-text_narrow">
          Гости
        </div>
        <img
          src="../assets/user.png"
          alt="user"
          class="availability__input-img"
        />
      </div>
      <a href="#" class="btn">
        Найти номер
      </a>
    </form>
    <img
      src="../assets/laces.png"
      alt=""
      class="availability__laces availability__after"
    />
  </div>
</template>

<script>
import DatePicker from "v-calendar/lib/components/date-picker.umd";

export default {
  components: {
    DatePicker
  },
  data() {
    return {
      mode: "single",
      startDate: new Date(),
      endDate: new Date(),
      guests: 1
    };
  }
};
</script>

<style lang="sass">
@import "../assets/sass/variables"

.availability
  width: 100%
  z-index: 0
  display: flex
  justify-content: flex-end
  @media only screen and (max-width : 1224px)
    width: 100%
  &__laces
    position: absolute
    right: 50%
    transform: translate(70%)
    top: -40px
    height: 40px
  &__after
    top: 100%
    transform: translate(70%) rotate(900deg)
    @media only screen and (max-width : 1224px)
      display: none
  &__inner
    width: 90%
    background-color: $creamy
    position: relative
    display: flex
    align-items: center
    padding: 10px 0
    padding-left: 13%
    &::before
        content: ""
        width: 100%
        height: 2px
        top: -5px
        left: 0
        background-color: $creamy-d
        position: absolute
    &::after
      content: ""
      width: 100%
      height: 2px
      bottom: -5px
      left: 0
      background-color: $creamy-d
      position: absolute
      @media only screen and (max-width : 1224px)
        display: none
    @media only screen and (max-width : 1224px)
      padding-left: 0
      justify-content: center
  &__title
    font-size: 30px
    margin-left: 135px
    margin-right: 30px
    @media only screen and (max-width : 1224px)
      margin-left: 0
  &__input-wrap
    margin-right: 24px
    position: relative
    input
      padding: 20px 10px 5px 50px
      width: 160px
      font: 500 18px $montserrat
      border: 0
      outline: 0
      border-radius: 3px
    .availability__guests-input
      text-align: center
      padding: 20px 0px 5px 45px
      width: 85px
  &__input-img
    position: absolute
    pointer-events: none
    left: 15px
    top: 50%
    transform: translateY(-50%)
  &__input-text
    position: absolute
    left: 51px
    top: 6px
    pointer-events: none
    font: 500 12px $montserrat
    &_narrow
      left: 42px
</style>
