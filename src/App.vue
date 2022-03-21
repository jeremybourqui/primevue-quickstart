<template>
  <div id="app">
    <div class="app-container">
      <img alt="Vue logo" src="./assets/primevue-logo.png">
      <HelloWorld msg="Welcome to Your PrimeVue App"/>
      <form @submit.prevent="greet">
        <InputText type="text" v-model="text"/>
        <Button type="submit" label="Submit"/>
        <h3>{{message}}</h3>
      </form>
      <Calendar v-model="value" />
      <ColorPicker v-model="color" />
          
            <div class="card">
            <h5>Nested</h5>
            <Splitter style="height: 300px">
                <SplitterPanel class="flex align-items-center justify-content-center" :size="20" :minSize="10">
                    Panel 1
                </SplitterPanel>
                <SplitterPanel :size="80">
                    <Splitter layout="vertical">
                        <SplitterPanel class="flex align-items-center justify-content-center" :size="15">
                            Panel 2
                        </SplitterPanel>
                        <SplitterPanel :size="85">
                            <Splitter>
                                <SplitterPanel class="flex align-items-center justify-content-center" :size="20">
                                    Panel 3
                                </SplitterPanel>
                                <SplitterPanel class="flex align-items-center justify-content-center" :size="80">
                                    Panel 4
                                </SplitterPanel>
                            </Splitter>
                        </SplitterPanel>
                    </Splitter>
                </SplitterPanel>
            </Splitter>
        </div>
    
    </div>

    <Toast/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Calendar from 'primevue/calendar';
import ColorPicker from 'primevue/colorpicker';
import Splitter from 'primevue/splitter';
import SplitterPanel from 'primevue/splitterpanel';

export default {
    data() {
        return {
            message: null,
            text: null,
            value: null,
            color: 'red'
        }
    },
    methods: {
        greet() {
            this.$toast.add({severity: 'info', summary: 'Hello '  + this.text});
            this.message = 'Hello ' + this.text;
        }
    },
    components: {
      HelloWorld,
      Calendar,
      ColorPicker,
      Splitter,
      SplitterPanel
    }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.app-container {
  text-align: center;
}

body #app .p-button {
  margin-left: .2em;
}

form {
  margin-top: 2em;
}
</style>