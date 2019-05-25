<template>
<div>
    <div class="row">
        <div class="col-sm-12">
                <h3>Quotes Added</h3>
                <div 
    class="progress-bar"
    :class="{
        'progress-bar-warning': quotesLength > 5,
        'progress-bar progress-bar-danger': quotesLength === 10
     }" 
    role="progressbar" 
    aria-valuenow="quotesLength" 
    aria-valuemin="0" 
    aria-valuemax="maxQuotes" 
    :style="{width: (quotesLength/maxQuotes * 100)+'%'}"
    >
      {{quotesLength}}/{{maxQuotes}}
    </div>
        </div>
    
</div>
</div>
 
</template>

<script>
    export default {
        props:["quotesLength","maxQuotes"]
    }
</script>

<style>
    .panel-body{
        font-family: 'Arizona',cursive;
        font-size: 24px;
        color: #6e6e6e;
    }
    .quote{
        cursor: pointer;
    }
    .quote:hover{
        background-color: #ffe2e2;
    }
</style>
