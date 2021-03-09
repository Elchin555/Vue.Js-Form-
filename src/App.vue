<template>
  <div class="container">
    <h3>Form</h3>
    <hr>
    <div class="row">
      <div class="col-md-6">
        <div class="panel panel-warning">
          <div class="panel-heading">
            <h4>Form</h4>
          </div>
          <div class="panel-body">
            <form>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label for="email" >Username</label>
                    <input type="text" id="username" class="form-control" v-model="userdata.username">
                  </div>
                  <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" class="form-control" v-model.lazy="userdata.password">
                  </div>
                  <div class="form-group">
                    <label for="age">Age</label >
                    <input type="number" id="age" class="form-control" v-model="userdata.age">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label for="message">Message</label><br>
                  <textarea id="message" rows="3" class="form-control" v-model="userdata.msg"></textarea>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label>
                      <input type="checkbox" value="Vue.js"   v-model="userdata.intresting"> Vue.js
                    </label>
                    <label>
                      <input type="checkbox" value="React.js" v-model="userdata.intresting"> React.js
                    </label>
                  </div>

                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label>
                    <input type="radio" value="Boy" v-model="userdata.gender"> Boy
                  </label>
                  <label>
                    <input type="radio" value="Women" v-model="userdata.gender"> Women
                  </label>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 from-group">
                  <label>City</label>
                  <select class="form-control" v-model="userdata.selectedCity">
                    <option :selected="cit=='qusar'" v-for="cit in userdata.citys">{{cit}}</option>
                  </select>
                </div>
              </div>
              <hr>
              <div class="row">
                <div class="col-md-12">
                  <button
                    class="btn btn-primary">Send!
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-6">
          <div class="panel panel-info">
            <div class="panel-heading">
              <h4>Form Data</h4>
            </div>
            <div class="panel-body">
              <p>Username:{{userdata.username}}</p>
              <p>Password:{{userdata.password}}</p>
              <p>Age:{{userdata.age}}</p>
              <p>Message:{{userdata.msg}} </p>
              <p><strong>Interest</strong></p>
              <ul >
                <li v-for="inter in userdata.intresting">{{inter}}</li>
              </ul>
              <p>Gender:{{userdata.gender}}</p>
              <p>City:{{userdata.selectedCity}}</p>
              <p>Toggle:</p>
            </div>
          </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
  data(){
    return{
      userdata:{
        username:"",
        password:"",
        age:"",
        msg:"",
        intresting:[],
        gender:"",
        selectedCity:"",
        citys:["baki","quba","qusar","sheki"]
    }
    }
  }
  }
</script>

<style>

</style>
