<template>
  <div class="container">
    <div class="mt-1">
      <Toast />

      <form @submit.prevent="greet">
        <InputText v-model="text" type="text" />
        <Button type="submit" label="Submit" />
      </form>
    </div>
    <hero />
    <LargeCardDisplay
      v-for="cardInfo in largeCardInfo"
      :key="cardInfo.id + new Date().getTime() - 2 - Math.random()"
      :cards-section="cardInfo"
    />
    <small-card-display
      v-for="cardInfo in smallCardSections"
      :key="cardInfo.id + new Date().getTime() - 1 - Math.random()"
      :cards-section="cardInfo"
    />
  </div>
</template>

<script>
import { largeCardSections, smallCardSections } from '@/assets/data.js'
import Hero from '~/components/Hero.vue'
import LargeCardDisplay from '~/components/LargeCardDisplay.vue'
import SmallCardDisplay from '~/components/SmallCardDisplay.vue'
export default {
  components: { Hero, LargeCardDisplay, SmallCardDisplay },
  data () {
    return {
      largeCardInfo: largeCardSections,
      smallCardSections,
      text: null
    }
  },
  methods: {
    greet () {
      this.$toast.add({ severity: 'info', summary: 'Hello ' + this.text })
    }
  }
}
</script>

<style>

</style>
