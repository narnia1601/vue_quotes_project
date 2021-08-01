<template>
    <div class="container mt-4">
        <app-header :quotes="quotes.length"></app-header>
        <app-new-quote @newQuote="newQuote" :quotes="quotes.length"></app-new-quote>
        <quote-grid :quotes="quotes"></quote-grid>
        <app-footer></app-footer>
    </div>
</template>

<script>
import Header from '../src/components/Header.vue'
import QuoteGrid from '../src/components/QuoteGrid.vue'
import Footer from '../src/components/Footer.vue'
import NewQuote from '../src/components/NewQuote.vue'
import { eventBus } from '../src/main'
    export default {
        data(){
            return{
                quotes: [
                    'Just a quote to start something with!'
                ],
                maxQuotes: 10,
            }
        },
        components: {
            QuoteGrid,
            appHeader: Header,
            appFooter: Footer,
            appNewQuote: NewQuote
        },
        methods: {
            newQuote(quote){
                this.quotes.push(quote)
            }
        },
        created(){
            eventBus.$on('quoteDeleted', (index) => {
                this.quotes.splice(index, 1)
            })
        }
    }
</script>

<style>
</style>
