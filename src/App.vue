<template lang="html">
  <div class="container-fluid">
    <tbody>
      <div class="row">
        <div v-for="family in families">
          <Family v-bind:family="family"></Family>
        </div>
      </div>
    </tbody>
  </div>
</template>

<script>
import Family from './components/Family.vue'
export default {
  data() {
    return {
      families: [{ photo: 'https://s3.ap-northeast-2.amazonaws.com/byeopssi/img/hanbyoel.jpg', names: ['김정훈', '고새롬', '김한별', '김한결']},
      { photo: 'https://s3.ap-northeast-2.amazonaws.com/byeopssi/img/saehan.jpg', names: ['강구윤', '이윤정', '강새한', '강새누']},
      { photo: 'https://s3.ap-northeast-2.amazonaws.com/byeopssi/img/chaebin.jpg', names: ['박영민', '신지영', '박채빈']},
      { photo: 'https://s3.ap-northeast-2.amazonaws.com/byeopssi/img/yeosung.jpg', names: ['이민환', '김은하', '이예성', '이예준']},
    ]
    }
  },
  components: {
      'Family': Family,
    }
}
</script>

<style lang="css">
</style>
