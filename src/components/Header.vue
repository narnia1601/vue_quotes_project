<template>
  <div>
      <h1>Quotes Added</h1>
      <div class="progress">
          <div class="progress-bar" :style="{ width: quotes * 10 + '%' }" aria-valuemin="0" aria-valuemax="10">{{ quotes }}/10</div>
      </div>
  </div>
</template>

<script>
export default {
    props: ['quotes']
}
</script>

<style>
    .progress-bar{
        transition: width 500ms;
    }
</style>