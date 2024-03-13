<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>

<!-- data binding -->
var vm = new Vue({
  el: '#databinding',
  data: {
    title : "Inline style Binding",
    activeColor: 'red',
    fontSize : 30
  }
});

<!-- conditional example (v-if) -->
<h1 v-if="awesome">Vue is awesome!</h1>

<template>
  <div>
    <my-component :my-prop="myData">
      <template v-slot:default="{ myFunction }">
        <button @click="myFunction()">Execute Function</button>
      </template>
      <template v-slot:footer>
        <p>Here's some contact info</p>
      </template>
    </my-component>
  </div>
</template>

<!-- props and slots-->
<script>
import MyComponent from './MyComponent.vue'

export default {
  components: {
    MyComponent
  },
  data() {
    return {
      myData: 'Hello, World!'
    }
  },
  methods: {
    myFunction() {
      alert(this.myData)
    }
  }
}

export default {
  props: {
    myProp: String
  },
  methods: {
    myFunction() {
      alert(this.myProp)
    }
  }
}
</script>

<!-- events -->
<button @click="counter++">Add 1</button>
	<p>The button above has been clicked {{ counter }} times.</p>

<!-- reactivity -->
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.myRef = null; 
  }

  componentDidMount() {
    // This will reference the DOM element
    console.log(this.myRef);
  }

  render() {
    return <div ref={(ref) => { this.myRef = ref; }}>Hello, world!</div>; 
  }
};

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
