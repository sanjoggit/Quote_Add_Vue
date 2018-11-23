<template>
<form>
    <div class="form-group">
        <label for="comment">Quote</label>
        <textarea class="form-control" rows="5" id="comment" v-model="quote"></textarea>
    </div>
    <div class="button">
        <button class="btn btn-primary" @click.prevent="createQuote">Add Quote</button>
    </div>
</form>
</template>
<script>
export default {
    data: function(){
        return{
            quote: ''
        }
    },
    methods: {
        createQuote: function(e){
           this.$emit('newQuote', this.quote)
        //    this.quote = ''
        }
    }
}
</script>
<style scoped>
    .form-group{
        width: 50%;
        margin: 0 auto;
    }
    .button{
        display: flex;
        justify-content: center;
        margin-top: 10px;
    }
</style>
