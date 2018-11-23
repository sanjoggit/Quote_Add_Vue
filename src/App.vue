<template>
    <div class="container">
        <app-header :quotes="quotes" :quoteMax="quoteMax"></app-header>
        <app-new-quote @newQuote="quoteAdd"></app-new-quote>
        <all-quotes :quotes="quotes" @deleteThisQuote="deleteQuote"></all-quotes>
        <div class="btn btn-info">Info: Click on a Quote to delete it</div>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import NewQuote from './components/NewQuote.vue';
import AllQuotes from './components/AllQuotes.vue'
    export default {
        data: function(){
            return{
                quotes: ['The best thing to hold onto in life is each other.'],
                quoteMax: 10,
            }
        },
        methods: {
            quoteAdd(quote){
                if(this.quotes.length >= this.quoteMax){
                    alert('you have reached the max limit');
                } else {
                    this.quotes.push(quote) 
                }
            },

            deleteQuote(i){
                this.quotes.splice(i, 1);
            }
        },
        components: {
            appHeader: Header,
            appNewQuote: NewQuote,
            allQuotes: AllQuotes
        }
    }
</script>

<style scoped>
    .btn{
        width: 100%;
    }
</style>
