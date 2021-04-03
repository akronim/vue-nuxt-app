<template>
  <div>
    <div class="container">
      <large-card-display
        v-for="cardInfo in largeCardInfo.slice(0, 1)"
        :key="cardInfo.id + new Date().getTime() - 2"
        :cards-section="cardInfo"
      />
      <small-card-display
        v-for="cardInfo in smallCardInfo.slice(0, 1)"
        :key="cardInfo.id + new Date().getTime() - 1"
        :cards-section="cardInfo"
      />
    </div>
  </div>
</template>

<script>
import { largeCardSections, smallCardSections } from '@/assets/data.js'
import LargeCardDisplay from '~/components/LargeCardDisplay.vue'
import SmallCardDisplay from '~/components/SmallCardDisplay.vue'
export default {
  components: { LargeCardDisplay, SmallCardDisplay },
  data () {
    return {
      largeCardInfo: largeCardSections,
      smallCardInfo: smallCardSections
    }
  }
}
</script>

<style scoped>
</style>
