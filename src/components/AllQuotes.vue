<template>
    <div class="row" >
        <div class="col-xs-6 col-sm-3" v-for="(quote, i) in quotes" v-bind:key=i >
            <div class="quote-container" @click="deleteQuote(i)">
             {{quote}}
            </div>
        </div>
    </div>  
    
</template>
<script>
export default {
    props: ['quotes'],

    methods: {
        deleteQuote:function(i){
            this.$emit('deleteThisQuote', i)
        }
    }
    
}
</script>
 <style scoped>
    .quote-container{
        border: 1px solid whitesmoke;
        padding: 15px;
        margin: 15px 0 15px 0;
        cursor: pointer;
    }
    .quote-container:hover{
        background-color: lightcoral;
    }
 </style>
 