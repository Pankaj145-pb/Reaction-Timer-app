<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      Click Me
  </div>
</template>

<script>
export default {
    data () {
        return{
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(()=> {
            this.showBlock = true;
            this.startTimer();

        }, this.delay)
    },

    methods:{
        startTimer () {
            this.timer = setInterval (()=> {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer () {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    },

props:['delay']
}
</script>

<style>
.block{
    width:400px;
    border-radius:20px ;
    background-color:blueviolet ;
    color: white;
    text-align: center;
    padding: 100px;
    margin: 40px auto;
}
</style>