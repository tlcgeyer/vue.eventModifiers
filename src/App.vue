<template> <!--make use of a div after temp-->
  <div>
    <form @submit.prevent="sendInfo">                                                                   
    <div>
      <label>Enter a value:</label>
      <input type="text" placeholder="Enter in here a value" v-model="currValue"> 
      <!--  @keyup="popUpMessage(currValue)"  this is only for the popUp to show (you can make use of enter by keyup to only show the popUp when you entered the value. ONCE only displays it once.(these are methods applied on your click event))-->
    </div>
    <div>
      <h2>List of entered values</h2> <!--creating a list where values are going to be entered. -->
      <ul v-show="listOfValues.length"> <!--if a list of values have a length show the values, if not nothing will be shown.  -->
      <li v-for="data, index in listOfValues" :key="index"> <!--for each element, index in the listOfValues, bind the key into the index. It also gives the index, placing the comma before will display it. 
      
      What is the function of key? 
    * to identify specific elements in a list
  
      What is the difference between a key and a value? 
      the value is the attribute you will assign -->
      <p>{{ data }} @position {{ index }}</p> 
      </li>
      </ul>
    </div>
    <button type="submit">Display</button>
    </form>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      currValue: '', //declaring the variables
      listOfValues: []
    }
  },
  components: {

  },
  methods: {      
    sendInfo() {  //function 
      if(this.currValue) {
        //checking if theres a value on currValue, then push it to the array
      this.listOfValues.push(this.currValue)  //in here
      }  
    },
    popUpMessage(arg) {
      alert(arg)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
