<template>
  <main class="container mt-5">
    <div class="row">
      <div class="col-12 text-right mb-4">
        <div class="d-flex justify-content-between">
          <h3>育てた水草一覧</h3>
          <nuxt-link to="/waterplants/add" class="btn btn-info">
            水草を追加する
          </nuxt-link>
        </div>
      </div>
      <template v-for="waterplant in waterplants">
        <div :key="waterplant.id" class="col-lg-3 col-md-4 col-sm-6 mb-4">
          <water-plant-card :onDelete="deleteWaterPlant" :waterplant="waterplant"></water-plant-card>
        </div>
      </template>
    </div>
  </main>
</template>

<script>
import WaterPlantCard from '~/components/WaterPlantCard.vue'

const sampleData = [
  {
    id: 1,
    name: 'パールグラス',
    position: '中景〜後景',
    picture: '/images/banner.jpg',
    difficulty: 'Easy',
    addition_amount: 'High',
    leaf_length: 2,
    water_quality: '弱酸性～中性  軟水～弱硬水'
  },
  {
    id: 2,
    name: 'キューバパールグラス',
    position: '前景',
    picture: '/images/banner.jpg',
    difficulty: 'Hard',
    addition_amount: 'High',
    leaf_length: 1,
    water_quality: '弱酸性～中性  軟水～弱硬水'
  },
  {
    id: 3,
    name: 'ニューラージパールグラス',
    position: '前景',
    picture: '/images/banner.jpg',
    difficulty: 'Medium',
    addition_amount: 'High',
    leaf_length: 1,
    water_quality: '弱酸性～中性  軟水～弱硬水'
  }
]

export default {
  head () {
    return {
      title: 'waterplants list'
    }
  },
  components: {
    WaterPlantCard
  },
  data () {
    return {
      waterplants: []
    }
  },
  asyncData (context) {
    let data = sampleData
    return {
      waterplants: data
    }
  },
  methods: {
    deleteWaterPlant (waterplant_id) {
      console.log(deleted`${waterplant.id}`)
    }
  }
}
</script>
<style scoped>
</style>
