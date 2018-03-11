<template>
  <div id="dice-roller">
    <span>
      <img v-for="dice in dices"  v-bind:class="{ rotate: isRolling, icon: true }"  :src="dice" :style="`background-color:${randomColor()}`"/>
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
    whiteBackground: {
      type: Boolean,
      default: false,
    },
  },
  watch: {
    count: function (newCount) {
      this.count = newCount
    },
    whiteBackground: function (n) {
      this.whiteBackground = n
    },
  },
  data () {
    return {
      dices: [],
      icons: defaultIcons.icons,
      isRolling: false,
      colors: [
        '#1664a2',
        '#2EC4B6',
        '#E71D36',
        '#FF9F1C',
        '#9c27b0',
        '#00bcd4',
        '#4caf50',
        '#9e9e9e',
      ],
    }
  },
  methods: {
    randomDice () {
      return this.icons[Math.round(Math.random() * (this.icons.length - 1))]
    },
    randomColor () {
      if (this.whiteBackground) {
        return
      }
      return this.colors[Math.round(Math.random() * (this.colors.length - 1))]
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
