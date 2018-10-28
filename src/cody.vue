<form v-if="!submitted"></form>

<div class="form-group" v-if="submitted">
  <label for="First Name"></label>
  <input type="text" class="form-control" v-model="firstName">
</div>
<div class="form-group">
  <label for="Last Name"></label>
  <input type="text" class="form-control" v-model="lastName">
</div>
<div class="form-group">
  <label for="Mail"></label>
  <input type="text" class="form-control" v-model="email">
</div>
<div class="form-group">
  <label for="Password"></label>
  <input type="text" class="form-control" v-model="password">
</div>
<div class="form-group">
  <label>
    <input type="radio" class="form-control" v-model="storeData">Yes
  </label>
  <label>
    <input type="radio" class="form-control" v-model="storeData">Yes
  </label>
</div>

<div>
  <p>Full Name: {{ firstName }} {{ lastName }}</p>
</div>

<button type="submit"
        class="btn btn-primary"
        @click.prevent="submitted = true"> Submit</button>

<script>
  export default {
    data () {
      return {
        firstName: 'Dallin',
        lastName: '',
        password: '',
        storeData: 'Yes',
        email: '',
        submitted: false
      }
    }
  }

</script>