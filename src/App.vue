<template>
    <div class="container">
        <ProgressBar 
        :quotesLength="quotes.length"
        :maxQuotes="maxQuotes"
        />
       
        <NewQuote  
            @quoteAdded="newQuote"
            :maxQuotes="maxQuotes"
            :quotesLength="quotes.length"
            />
        <QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"/>
        <div>
            <div class="col-sm-12 text-center">
                <div class="alert alert-info" v-if="quotes.length < maxQuotes">
                    click quote to delete
                </div>
                <div class="alert alert-danger" v-else>
                    You have to delete a quote to add a new quote
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from "./components/QuoteGrid.vue";
    import NewQuote from "./components/NewQuote.vue";
    import ProgressBar from "./components/ProgressBar.vue";
    export default {
        components:{
            QuoteGrid,
            NewQuote,
            ProgressBar
        },
        data(){
            return{
                maxQuotes: 10,
                quotes: []
            }
        },
        methods:{
            newQuote(quote){
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        }
    }
</script>

<style>
</style>
