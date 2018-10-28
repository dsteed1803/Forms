<template>
  <div class="container">
    <form v-if="!isSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Part 1 5 Points-->
          <!-- Create a Signup Form where you retrieve the following Information -->

          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->

          <!-- Part 2 5 Points -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Part 3 5 Points -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name:</p>
            <input type="text"
                   v-model="userData.firstName">
            <input type="text"
                   v-model="userData.lastName">
            <br>
            <hr>
            <p>Mail:</p>
            <input type="text"
                   v-model="userData.email">
            <p>Password:</p>
            <input type="password"
                   v-model="userData.password">
            <p>Store in Database?: </p>
            <div class="row">
              <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <app-switch v-model="dataSwitch"></app-switch>
              </div>
            </div>
              <button
                  class="btn btn-primary"
                  @click.prevent="isSubmitted=true">Submit!
              </button>            
          </div>
        </div>
      </div>
    </div>
    </form>
    <hr>
    <div class="row"  v-if="isSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ userData.firstName}} {{ userData.lastName }}</p>
            <p>Mail: {{ userData.email }}</p>
            <p>Password: {{ userData.password }}</p>


          </div>
        </div>
      </div>
    </div>
    </div>
</template>

<script>
  import Switch from './Switch.vue';
  export default {
    data () {
      return {
        userData: {
          firstName: '',
          lastName: '',
          email: '',
          password: '',
          dataSwitch: true
        },
        isSubmitted: false
      }
    },
    components: {
          appSwitch: Switch
    },

    methods: {
      submitted () {
        this.isSubmitted = true;
      }
    }
  }
</script>

<style>
</style>
