<template>
    <div class="mt-2">
        <div class="form-group">
            <label for="exampleFormControlTextarea1">Example textarea</label>
            <textarea class="form-control mt-2" id="exampleFormControlTextarea1" rows="2" v-model="newQuote"></textarea>
            <div class="text-center"><button class="btn btn-primary mt-3" @click="submitQuote">Add Quote</button></div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            newQuote: '',
        }
    },
    methods: {
        submitQuote(){
            if(this.quotes < 10 && this.newQuote != ''){
                this.$emit('newQuote', this.newQuote)
                this.newQuote = ''
            }else if(this.newQuote == ''){
                alert('Please enter a quote before submitting')
            }else{
                alert('Maximum number of quotes have been reached')
            }
        }
    },
    props: ['quotes']
}
</script>

<style>

</style>