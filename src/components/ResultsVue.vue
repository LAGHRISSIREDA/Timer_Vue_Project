<template>
  <p class="score">Reaction Time : {{score}} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
props:['score'],
data(){
    return{
        rank:null
    }
},
mounted(){
    if(this.score<240){
        this.rank = 'You have a ninja  fingers'
    }else if(this.score<400){
        this.rank ='Great Work'
    }else{
        this.rank ='Make effort'
    }
}
}
</script>

<style  scoped>
    .rank{
        text-decoration: underline;
        font-size: 2em;
        color: chartreuse;
        animation: colors 1s infinite;
    }

    @keyframes colors {
        0%{color: chartreuse;}
        25%{color: rgba(251, 40, 21, 0.979);}
        50%{color: rgb(5, 142, 255);}
        75%{color: rgb(230, 29, 73);}
        100%{color: chartreuse;}
        
    }
    .score{
        font-weight: bold;
        margin-top: 1em;
        font-size: 2em;
    }
</style>