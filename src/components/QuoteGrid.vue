<template>
  <div class="row">
    <div class="col-3" v-for="(quote, index) in quotes" :key="quote">
      <quote :quote="quote" :quotes="quotes" :index="index">
        <h4>{{ quote }}</h4>
      </quote>
    </div>
  </div>
</template>

<script>
import Quote from '../components/Quote.vue'
export default {
    props: ['quotes'],
    components: {
      Quote
    }
}
</script>

<style>

</style>