<template>
<br>
<div> Reaction time {{ score }}</div>
<p class="rank"> you got {{ rank }}</p>
</template>

<script>
export default {
    data () {
        return{
            rank: null
        }
    },
props: ['score'],
mounted () {
    if(this.score < 250){
        this.rank = "Ninja Fingers"
    }
    else if(this.score < 450) {
        this.rank = "Rapid reflexes"
    }
    else{
        this.rank = "Turtle pace"
    }
}
}
</script>

<style>
.rank{
    color:crimson
}
</style>