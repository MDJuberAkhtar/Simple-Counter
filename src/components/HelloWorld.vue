<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{output}}</p>
    <button class="buton" @click="increase">Change</button>

    <div class="healthbar">
      <div class="healthbar text-center" style="background-color: green; margin: 0; color: white;" :style="{width: counter*5+'%'}">
        {{counter*5}}
      </div>
    </div>
  
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    counter: Number
  },
  computed:{
    output(){
     return this.counter;
  }
},
watch:{
  counter(){
   alert('Value has changed')
  }
},

methods:{
  increase(){
    this.counter++;
    if(this.counter >20){
      this.counter = 0;
    }
  }
}


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.text-center {
    text-align: center;
}

.healthbar {
    width: 80%;
    height: 20px;
    background-color: #eee;
    margin: auto;
    transition: width 500ms;
}

.buton{
  margin-bottom: 10px;
}

</style>
