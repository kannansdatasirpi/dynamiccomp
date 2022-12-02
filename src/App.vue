<!--Dynamic components switch between the components(we can think of it as navigating between pages on regular website) 
Dynamic components allow us to switch between two or more components without using routing 
Dynamic components can retains data state.
-->
<template>
  <div id="home">
  <button @click="activeStep = 'HomePage'">Home</button>
  <button @click="activeStep = 'AboutUs'">About US</button>
  <button @click="activeStep = 'ContactUs'">Contact US</button>
  </div>
<!--step2 add component-->
<keep-alive>
  <component :is="activeStep"/> 
</keep-alive>
  <!--single component ele bind these prop to it and bcz activestep contain the component name we can use it--> 

<!--step1-->
<!-- <div id="dir">
  <HomePage v-if="activeStep === 'HomePage'"/>
  <AboutUs v-if="activeStep === 'AboutUs'"/>
  <ContactUs v-if="activeStep === 'ContactUs'"/>
</div> -->
<!--in v-if concept we could encounter some issuses. 1st problem is multistep forms will often have many steps. its lot of unnecessary code and also gives us an opportunity to make mistakes 
2nd problem is that data doesn't persist from one compon another wihich is necessary in a multi step form-->
</template>

<script>
import HomePage from './components/HomePage.vue'
import AboutUs from './components/AboutUs.vue'
import ContactUs from './components/ContactUs.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    AboutUs,
    ContactUs,
  },
  data() {
    return {
      activeStep: "HomePage",

      // activeStep: "AboutUs",activeStep: "ContactUs",

      //here i am facing one challenges, i return a data property using a same name(activeStep) in 3 times. it's occure a eslint error duplicate keyword then i remove the two property name.then it's solve.
      
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
button{
  background: green;
  color:#fff;
  border: 1px solid #fff;
  padding: 10px 10px 10px 10px;
  font-size: 14px;
}
button:hover {
  cursor:pointer;
}

</style>
