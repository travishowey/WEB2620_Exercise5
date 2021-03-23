<template>
  <div class="container">
    <form>
      <div class="row"
      v-if="!isSubmitted">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <h1>Sign Up Form</h1>
          <hr>
          <div class=“form-group”>
            <label for=“fullName”>Full Name</label>
            <input
              type=“text”
              id=“fullName”
              class=“form-control”
              v-model.lazy="userData.fullName"
              >
          </div>
          <div class=“form-group”>
            <label for=“email”>Mail</label>
            <input
              type=“text”
              id=“email”
              class=“form-control”
              v-model.lazy="userData.email"
            >
          </div>
          <div class=“form-group”>
            <label for=“password”>Password</label>
            <input
              type="password"
              id=“password”
              class=“form-control”
              v-model.lazy="userData.password"
              >
          </div>
          <label for=“yes”>
            <input 
            type="radio"
            id=“yes”
            value=“Yes”
            v-model="storeData">
          Yes
          </label>
          <label for=“no”>
            <input
            type="radio"
            id=“no”
            value=“No”
            v-model="storeData">
          No
          </label>
          <br>
          <app-switch v-model="dataSwitch"></app-switch>
          <button
            class="btn btn-primary"
            @click.prevent="submitted"
          >Submit
          </button>
        </div>
      </div>
    </form>
    <hr>
    <br>
    <div 
    class="row"
    v-if="isSubmitted"
    >
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.fullName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>
            <p>Store in Database?: {{ storeData }} </p>
            <p>Switched: {{ dataSwitch }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Switch from './Switch.vue'
export default {
  data () {
    return {
      userData: {
        fullName: '',
        email: '',
        password: '',
      },
      storeData: 'Yes',
      dataSwitch: true,
      isSubmitted: false
    }
  },
methods: {
  submitted () { 
    this.isSubmitted = true
  }
},
components:
{
  appSwitch: Switch
}
}
</script>


<style></style>
