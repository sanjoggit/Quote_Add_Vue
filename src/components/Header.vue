<template>
<div>
    <h2>Quotes Added</h2>
    <div class="progress">
        <div class="progress-bar" 
        role="progressbar" 
        v-bind:style="{width: (quotes.length/quoteMax) * 100 +'%'}" 
        aria-valuenow="25" 
        aria-valuemin="0" 
        aria-valuemax="100">{{quotes.length}}/10</div>
    </div>
</div>
</template>
<script>
export default {
    props: ['quotes', 'quoteMax']
}
</script>
<style>
</style>
