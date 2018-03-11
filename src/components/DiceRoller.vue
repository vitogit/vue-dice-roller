<template>
  <div id="dice-roller">
    <span>
      <img v-for="dice in dices"  v-bind:class="{ rotate: isRolling, icon: true }"  :src="dice"/>
    </span>
  </div>
</template>

<script>
import defaultIcons from './_icons.js'
export default {
  name: 'dice-roller',
  props: {
    count: {
      type: Number,
      default: 5,
    },
  },
  watch: {
    count: function (newCount) {
      this.count = newCount
    },
  },
  data () {
    return {
      dices: [],
      icons: defaultIcons.icons,
      isRolling: false,
    }
  },
  methods: {
    randomDice () {
      return this.icons[Math.round(Math.random() * (this.icons.length - 1))]
    },
    roll () {
      this.isRolling = !this.isRolling
      this.dices = []
      for (var i = 0; i < this.count; i++) {
        var dice = this.randomDice()
        this.dices.push(dice)
      }
    },
  },
  mounted () {
    this.roll()
  },
}
</script>

<style>
  .icon {
    width: 50px;
    height: 50px;
    border: 3px solid #000;
    border-radius: 5px;
    cursor: pointer;
    margin: 10px;
    -moz-transition: all 1s linear;
    -webkit-transition: all 1s linear;
    transition: all 1s linear;
  }

  .icon.rotate{
    -ms-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
</style>
