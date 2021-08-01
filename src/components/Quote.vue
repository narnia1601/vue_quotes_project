<template>
  <div>
      <div class="card mt-4" @click="deleteQuote">
        <div class="card-body">
            <slot></slot>
        </div>
      </div>
  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
    props: ['quote', 'quotes', 'index'],
    methods: {
        deleteQuote(){
            eventBus.$emit('quoteDeleted', this.index)
        }
    }
}
</script>

<style>
    .card:hover{
        background-color: rgba(255, 0, 0, 0.5);
        cursor: pointer;
    }
</style>