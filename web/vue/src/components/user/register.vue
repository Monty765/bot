<template lang='jade'>
  section.contain.grd-row
    .grd-row-col-3-6(v-html='left')
    .grd-row-col-3-6.txt--center
        h4.form-signin-heading Sign Up

        form(method='POST',@submit="checkForm")
          div.form-group
            input#email.form-control(type='email', placeholder='name@email.com', name='email',v-model="email",required)
          div.form-group
            input#pw.form-control(type='password' name='password', placeholder='Password',v-model="password",required)
          div.form-group
            span.passerrors
            input#pw2.form-control(type='password' name='confirmPassword', placeholder='Confirm Password',v-model="confirmpassword" required)
          button.btn--primary(v-on:click="onSubmit" type='submit') Sign up



</template>

<script>
import marked from '../../tools/marked';
import { basePath } from '../../tools/api';

const left = marked(`

## xxbotss

`);
var temp = false;

export default {
  data: () => {
    return {
      left,
      errors:[],
    }
  },
  computed: {
    imageUrl: function() {
      return basePath + 'assets/gekko.jpg';
    }
  },
  methods: {
    checkForm:function(e) {
      console.log(this.confirmpassword);
      if(this.email && this.password && this.confirmPassword) return true;
      this.errors = [];
      if(!this.email) this.errors.push("Valid email is required");
      if(!this.password) this.errors.push("Password required");
      e.preventDefault();
    },
    onSubmit: function (e) {
      var credentials = {
          username: this.email,
          password: this.password,
          confirmpassword: this.confirmpassword
        }
        var data = '?uname='+this.email+'&pwd='+this.password;
        temp = true;
        this.$http.get('http://localhost:8081/xbot/users.php'+data, {foo: 'bar'}, {
          method: 'GET',
          headers: {
             "Accept": "application/json, text/plain, */*",
             "Authorization": "Basic YXBpOnBhc3N3b3Jk",
             "X-Requested-With": "XMLHttpRequest"
         },
        })
    }
  }
}



</script>

<style>

label{
  font-size: 12px;
  width: 130px;
  float: left;
}
input{
  width: 70%;

}

</style>
