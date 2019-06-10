<template>
  <div id="app" class="container">

    <b-container fluid>
      <b-jumbotron header="Калькулятор проката технических средств реабилитации" header-level="6" bg-variant="light">
        <b-row>
        <b-col sm="2"><img alt="Vue logo" src="./assets/logo_pcson.png"></b-col>
        <b-col><p>Приморский центр социального обслуживания населения</p></b-col>
        </b-row>
      </b-jumbotron>
    </b-container>

    <b-form @submit="onSubmit" v-if="showForm">

      <Equipment :equipments="equipments" @equipmentSelect="setEq($event)"/>
      <DaysRent @newDays="setDays($event)" />
      <Privileges :privileges="privileges" @pickedOpt="setPriv($event)"/>

      <div id="app-sum">
      <b-input-group id="cost-sum" size="lg" prepend="Сумма, руб." append=".00">
        <b-form-input v-model="form.sum"></b-form-input>
      </b-input-group>
      Selected: {{ form.selected ? form.selected.name : null }}, Days: {{ form.days }}, Privileges: {{ form.priv ? form.priv.title : "Без льгот" }}
      </div>

      <b-input-group id="phone" prepend="Телефон: " class="mt-3">
        <b-form-input v-model="form.phone" id="phonenum" placeholder="8(xxx)xxx-xx-xx"></b-form-input>
        <b-input-group-append>
          <b-button type="submit" variant="outline-success">Отправить заявку</b-button>
        </b-input-group-append>
      </b-input-group>

    </b-form>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Equipment from './components/Equipment.vue'
import DaysRent from './components/DaysRent.vue'
import Privileges from './components/Privileges.vue'

import equipments from '@/data/tsr-equipment.json'
import privileges from '@/data/tsr-privileges.json'


export default {
  name: 'app',
  components: {
    // HelloWorld,
    Equipment,
    DaysRent,
    Privileges
  },
  data(){
    return {
      equipments,
      privileges,
      showForm: true,
      form: {
        equipment: Object,
        days: 0,
        priv: privileges[0],
        sum: 0,
        phone: 8000000000
      }
    }
  },
  methods: {
    setEq(item) {
      this.form.equipment = this.equipments[this.equipments.findIndex(x=>x.id == item)]
      this.calculate()
      },
    setDays(item){
      this.form.days = item
      this.calculate()
    },
    setPriv(item){
      this.form.priv = privileges[item]
      this.calculate()
    },
    calculate(){
      if(this.form.equipment) {
        this.form.sum = this.form.priv.id == 0 || this.form.priv == null ? (this.form.days * this.form.equipment.price) : (this.form.days * this.form.equipment.price) / 2
      }
    },
    onSubmit(evt) {
      evt.preventDefault()

      alert(JSON.stringify(this.form))

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}

  #app-sum {
    position: sticky;
    bottom: 20px;
  }
</style>
