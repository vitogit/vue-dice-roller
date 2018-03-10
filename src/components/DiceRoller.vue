<template>
  <div id="dice-roller">
    <!-- <span v-if="diceFaces">
      <span v-for="dice in dices"> </span>
    </span> -->

    <span>
      <img v-for="dice in dices"  class="icon" :src="dice"/>
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
    diceFaces: {
      type: Number,
      default: null
    }
    // faces: {
    //   type: Number,
    //   default: 6,
    // }
  },
  watch: {
    // fen: function (newFen) {
    //   this.fen = newFen
    //   this.loadPosition()
    // },
  },
  data () {
    return {
      dices: [],
      icons: defaultIcons.icons,
    }
  },
  methods: {
    randomDice () {
      return this.icons[Math.round(Math.random() * (this.icons.length - 1))]
    },
    initDices () {
      this.dices = []
      console.log('this.count', this.count)
      for (var i = 0; i < this.count; i++) {
        var dice = this.randomDice()
        console.log("dice",dice)
        this.dices.push(dice)
      }
    },
  },
  mounted () {
    console.log("defaultIcons",defaultIcons)
    this.initDices()
    console.log('this.dices', this.dices)
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
    margin: 2px;
  }
</style>
