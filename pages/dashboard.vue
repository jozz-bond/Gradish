  <template>
  <!--div class="container"-->
    <div>
      <!--header class="content-logos">
        <logo />
        <span class="plus">+</span>
        <VuesaxLogo />
      </header-->

      <h1 class="title">Dashboard</h1>
      <!--div class="links">
        <h3 class="h3">Vuesax</h3>
        <a href="https://vuesax.com/" target="_blank" rel="noopener noreferrer" class="button--green">Documentation</a>
        <a href="https://github.com/lusaxweb/vuesax" target="_blank" rel="noopener noreferrer"  class="button--grey">GitHub</a>
      </div-->

      <div class="row">
        <div class="column-third">
          <div class="card">
            <img src="img_avatar.png" alt="Avatar" style="width:100%">
            <div class="container-card">
              <h4><b>My Tracker Overview</b></h4> 
                <vs-button size="xl" :active="active == 0" @click="active = 0"> XLarge </vs-button>
            </div>
          </div>
        </div>
        <div class="column-third">
          <div class="card">
            <img src="img_avatar.png" alt="Avatar" style="width:100%">
            <div class="container-card">
              <h3>Company list</h3> 
                <vs-button size="xl" :active="active == 0" @click="active = 0"> XLarge </vs-button>
            </div>
          </div>        </div>
        <div class="column-third">
        <div class="card">
          <img src="img_avatar.png" alt="Avatar" style="width:100%">
          <div class="container-card">
            <h4><b>John Doe</b></h4> 
              <vs-button size="xl" :active="active == 0" @click="active = 0"> XLarge </vs-button>
          </div>
        </div>        </div>
      </div>
      <div class="links">
        <h3 class="h3">Nuxt.js</h3>
      </div>
    </div>
  <!--/div-->
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuesaxLogo from "~/components/VuesaxLogo.vue";

export default {
  components: {
    Logo,
    VuesaxLogo,
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 55px;
  color: #35495e;
  letter-spacing: 1px;
  text-transform: capitalize;
  margin: 25px 0;
}

.subtitle {
  font-weight: 300;
  font-size: 1.1rem;
  color: #526488;
  word-spacing: 2px;
  padding-bottom: 15px;
  max-width: 600px;
}

.subtitle a {
  font-weight: 500;
  color: inherit;
}

.column-third {
  float: left;
  width: 33.33%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

.content-logos {
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 500px;
}

.plus {
  font-size: 2.5rem;
  margin: 15px;
  color: #35495e;
}

.h3 {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-weight: 400;
  margin: 10px;
}

.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 95%;
  border-radius: 25px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container-card {
  padding: 16px 16px;
}
</style>
