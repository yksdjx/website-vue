<template>
<div class="container-fluid">
    <div class="login">
        <form class="form-horizontal" action="/login.do" method="post" v-on:submit.prevent="submit()">
            <fieldset>
                <legend>login</legend>


                <div class="form-group">
                    <label for="inputuserName3" class="col-sm-2 control-label">userName</label>
                    <div class="col-sm-10">
                        <input type="text" name="username"  class="form-control" id="inputuserName3" placeholder="userName" v-model="username" />
                    </div>
                </div>
                <div class="form-group">
                    <label for="inputPassword3" class="col-sm-2 control-label">Password</label>
                    <div class="col-sm-10">
                        <input type="password"  name="password" class="form-control" id="inputPassword3" placeholder="Password" v-model="password" />
                    </div>
                </div>
                <div class="form-group">
                    <div class="col-sm-offset-2 col-sm-10">
                        <div class="checkbox text-left">
                            <label>
                              <input type="checkbox"> Remember me
                            </label>
                        </div>
                    </div>
                </div>
                <div class="form-group">
                    <div class="col-sm-offset-2 col-sm-10">
                        <button type="submit" class="btn btn-default">Sign in</button>
                    </div>
                </div>
            </fieldset>
        </form>
    </div>
</div>
</template>

<script>
export default {
    name: 'login',
    data() {
        return {
            msg: 'Welcome to Your Vue.js App',
            username:'',
            password:''
        }
    },
    methods: {
        submit: function(e){
            //var formData = this.data();
            //console.log(this._data)
            this.$http.post('/someUrl', '', { emulateJSON: true}).then((response) => {
                // success callback
            }, (response) => {
                // error callback
            });
        }
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
    font-weight: normal;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
.login{
    width: 500px;
    margin: 20px auto;
}
</style>
