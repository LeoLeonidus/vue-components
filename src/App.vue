<template>
  <Greet name="Giorgio" heroName="Babbio"/>
  <Greet name="Filippo" heroName="Topogigio"/>
  <Greet v-bind:name="name" :heroName="job"/>

  <!-- id is a NON PROPS attidute -->
  <Article id="my-id" title="The Title" :like="3" :isPublished="true"/>

  <!-- PROVIDE / INJECT -->
  <h2>App component userName is {{loginName}}</h2>
  <ComponentC />

  <!-- CUSTOM EVENT -->
  <button @click="showPopUp = true" >Show PopUp Component</button>
  <!-- @close is the custom event emitted from the child PopUp component -->
  <PopUp v-show="showPopUp" @close="closePopUp(name)"/>

  <!-- INPUT CUSTOM COMPONENTS and V-MODEL -->
  <h2>Input Custom Components and v-model</h2>
  <InputComponent v-model="myName"/>

  <!-- SLOT -->
  <h2>SLOT</h2>
  <Card></Card>
  <Card>Card Content</Card>
  <Card>
    <h2>Card Content</h2>
  </Card>
  <Card>
    <img src="https://picsum.photos/200" alt="">
  </Card>
  <Card>
    <template v-slot:header>
      <h3>Header</h3>
    </template>
    <template v-slot:default>
      <img src="https://picsum.photos/200" alt="">
    </template>
    <template v-slot:footer>
      <button>Click Footer Button</button>
    </template>
  </Card>
  <h2>NameList Component</h2>
  <NameList>
    <template v-slot:default="slotProps">
        {{slotProps.firstName}} {{slotProps.lastName}}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{slotProps.lastName}} {{slotProps.firstName}}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{slotProps.firstName}}
    </template>
  </NameList>

  <hr>
  <h4>App Component Text - Child Styles</h4>
  <ChildStyles>
    <h4>ChildStyles Component Text</h4>
  </ChildStyles>

  <hr>
  <h2>Dynamic Components</h2>
  <button @click="activeTab='TabA'">TabA</button>
  <button @click="activeTab='TabB'">TabB</button>
  <button @click="activeTab='TabC'">TabC</button>
  <KeepAlive>
    <component :is="activeTab" />
  </KeepAlive>
  <!-- <TabA v-if="activeTab === 'TabA'"/>
  <TabB v-if="activeTab === 'TabB'"/>
  <TabC v-if="activeTab === 'TabC'"/> -->

    <hr>
  <!-- TELEPORT COMPONENT -->
  <!-- portal-root è un nuovo tag DIV in index.html : <div id="portal-root"></div> -->
  <teleport to="#portal-root">
    <Portal />
  </teleport>
  


  <br/>
  <br />
  <br />
</template>

<script>
import Greet from './components/Greet.vue'
import Article from './components/Article.vue'
import ComponentC from './components/ComponentC.vue'
import PopUp from './components/PopUp.vue'
import InputComponent from './components/InputComponent.vue'
import Card from './components/Card.vue'
import NameList from './components/NameList.vue'
import ChildStyles from './components/ChildStyles.vue'
import TabA from './components/TabA.vue'
import TabB from './components/TabB.vue'
import TabC from './components/TabC.vue'
import Portal from './components/Portal.vue'

export default {
  name: 'App',
  components: {
    Greet,
    Article,
    ComponentC,
    PopUp,
    InputComponent,
    Card,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    Portal
  },
  data() {
    return {
      name: 'Mario',
      job: 'homeless',
      loginName: 'Gigetto',
      showPopUp: false,
      myName: 'Filippo',
      activeTab: 'TabA'
    }
  },
  methods :{
    closePopUp(name) {
      this.showPopUp = false
      console.log("name : ",name)
    }
  },
  provide() {
    return {
      userName: this.loginName // provide/inject
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
h4 {
  color: orange;
}
</style>
