<template>
<!--STUDENT LOGIN PAGE-->
<!--LoginPage.vue-->
    <div class="content">
      <div class="containter-fluid">
        <div class="row d-flex justify-content-center">
            <card class="card-user col-md-4 m-5 shadow-lg">
              <div class="card-header text-md-center">  <!--text-md-center-->
                  <h4>ATTENDANCE TRACKER</h4>
              </div>
              <div class="card-content">
                <form>
                  <div class="row justify-content-center">
                    <div class="col-md-8">
                      <base-input type="email" 
                                label="Username"
                                placeholder="Enter email address" 
                                aria-placeholder="Enter email address">
                      </base-input>
                    </div>
                  </div>
                  <div class="row justify-content-center">
                    <div class="col-md-8">
                      <base-input type="password" 
                                label="Password"
                                placeholder="Enter password" 
                                aria-placeholder="Enter email address">
                      </base-input>
                    </div>
                  </div>                  
                </form>
              </div>
              <div class="card-footer mb-5">
                <router-link to="/admin/overview">
                  <button class="btn btn-lg btn-block" 
                    id="Login" type="submit">Login
                  </button>
                </router-link> 
              </div>
            </card>
        </div>
      </div>
    </div>
</template>

<script>
export default{
    name: 'LoginPage',
}
</script>

<style scoped>
#Login{
    background-color: #284265;
    border-bottom: #284265;
    color: aliceblue;
}   

</style>
