<template>
  <div class="container">
    <h3>Forms</h3>
    <hr>
    <div class="row">
      <div class="col-md-6">
        <div class="panel panel-warning">
          <div class="panel-heading">
            <h4>Application Form</h4>
          </div>
          <div class="panel-body">
            <form>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label for="email">UserName</label>
                    <input type="text" v-model.lazy="UserData.username" id="username" class="form-control">
                  </div>
                  <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" v-model.lazy="UserData.password" id="password" class="form-control">
                  </div>
                  <div class="form-group">
                    <label for="age">Age</label>
                    <input type="number" v-model.lazy="UserData.age" id="age" class="form-control">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label for="message">Message</label><br>
                  <textarea id="message" v-model.lazy="UserData.message" rows="3" class="form-control"></textarea>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label>
                      <input v-model="UserData.checkbox" type="checkbox" value="software"> Software
                    </label>
                    <label>
                      <input v-model="UserData.checkbox" type="checkbox" value="hardware"> Hardware
                    </label>
                  </div>

                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label>
                    <input v-model.lazy="UserData.gender" type="radio" value="male"> Male
                  </label>
                  <label>
                    <input v-model.lazy="UserData.gender" type="radio" value="female"> Female
                  </label>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 from-group">
                  <label>Cıty</label>
                  <select v-model="UserData.selectedCity" class="form-control">
                    <option  v-for="city in UserData.cities">{{city}}</option>
                  </select>
                </div>
              </div>
              <hr>
              <div class="row">
                <div class="col-md-12">
                  <button
                    @click.prevent="submit"
                    class="btn btn-primary">Submıt!
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-6" v-if="isSubmit">
          <div class="panel panel-info">
            <div class="panel-heading">
              <h4>Form Datas</h4>
            </div>
            <div class="panel-body">
              <p>Username: {{UserData.username}}</p>
              <p>Password: {{UserData.password}}</p>
              <p>Age: {{UserData.age}}</p>
              <p>Message: {{ UserData.message}}</p>
              <p><strong>areas of interest</strong></p>
              <ul>
                <li v-for="item in UserData.checkbox">{{item}}</li>
              </ul>
              <p>Gender: {{UserData.gender}}</p>
              <p>Cıty: {{UserData.selectedCity}}</p>
            </div>
          </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
  data(){
        return {
          UserData: {
            username: "",
            password : "",
            age : null,
            cities :['Rzeszow','Wroclaw','Warsaw','Lodz','Poznan'],
            gender : "",
            checkbox : [],
            message: "",
            selectedCity: "",
          },
          isSubmit: false
        }
      },
    methods: {
      submit(){
        this.isSubmit = true;
      }
    }
  }
</script>

<style>

</style>
