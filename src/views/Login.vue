<template>
  <div class="container">
    <div class="row">
      <div class="centered">
        <img src="@/assets/way2go-logo.png" alt="Logo Way2Go">

        <hr>

        <!-- ============================= -->
        <!-- == LOGIN FORM =============== -->
        <!-- ============================= -->
        <form
          v-if="form === 'login'"
          class="form-group"
          novalidate="true"
        >
          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-envelope" /></span>
            </div>
            <input
              type="email"
              required="true"
              class="form-control form-input"
              placeholder="Adresse mail"
            >
          </div>

          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-lock" /></span>
            </div>
            <input
              type="password"
              required="true"
              class="form-control form-input"
              placeholder="Mot de passe"
            >
          </div>

          <!-- <img src="@/assets/google-login-btn.png" alt="Logo Way2Go"> -->

          <button
            type="submit"
            class="btn btn-primary"
            style="width: 250px"
          >
            <i class="fas fa-sign-in-alt fa-spacer" />
            Se connecter
          </button>

          <hr>

          <div class="text-center">
            <span class="small link">Mot de passe oublié ?</span>
            <span
              class="small link"
              @click="form = 'register'"
            >Créer un compte !</span>
          </div>
        </form>

        <!-- ============================= -->
        <!-- == REGISTER FORM ============ -->
        <!-- ============================= -->
        <form
          v-if="form === 'register'"
          class="form-group"
        >
          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-user" /></span>
            </div>
            <input
              type="text"
              required="true"
              class="form-control form-input"
              placeholder="Nom d'utilisateur"
            >
          </div>

          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-envelope" /></span>
            </div>
            <input
              type="email"
              required="true"
              class="form-control form-input"
              placeholder="Adresse mail"
            >
          </div>

          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-lock" /></span>
            </div>
            <input
              type="password"
              required="true"
              class="form-control form-input"
              placeholder="Mot de passe"
            >
          </div>

          <div class="input-group mb-3">
            <div class="input-group-prepend">
              <span
                class="input-group-text form-input"
                style="height: 30px"
              ><i class="fas fa-lock" /></span>
            </div>
            <input
              type="password"
              required="true"
              class="form-control form-input"
              placeholder="Confirmation mot de passe"
            >
          </div>

          <button
            type="submit"
            class="btn btn-primary"
            style="width: 250px"
          >
            <i class="fas fa-user-plus fa-spacer" />
            S'inscrire
          </button>

          <hr>

          <div class="text-center">
            <span
              class="small link"
              @click="form = 'login'"
            >Vous avez déjà un compte ?</span>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import router from '../router'

export default {
  data () {
    return {
      // tab management
      form: 'login'
    }
  },
  computed: {
  },
  mounted () {
  },
  methods: {
    login: async function () {
    },
    register: async function () {
    },
  }
}
</script>

<style scoped>
.alert {
  text-align: left !important;
}

.roboto {
  font-family: 'Roboto', sans-serif !important;
}

.fa-spacer {
  padding-right: 10px
}

.title {
  /* color: #639BC0; */
  font-size: 40px;
  font-weight:bold;
}

hr {
  margin: 30px
}

.link {
  color: rgb(177, 72, 89);
  display: block;
  text-decoration: none;
  position: relative;
  text-transform: uppercase;
  text-decoration: none;

  display: inline-block;
  padding: 5px 10px;
  position: relative;
}

/* Centrage vertical & horizontal */
.centered {
  top: 50%;
  left: 50%;
  width: 250px;
  position: absolute;
  text-align: center;
  transform: translate(-50%, -50%);
}

img {
  width: 100%;
  height: 100%;
}

.form-input {
  padding: 30px;
  padding-left: 15px;
  padding-right: 15px;
  color: #3a3a3a;
  border: 1px solid #f0f0f0;
}

.btn {
  border: none;
  height: 50px;
  width: 175px;
  transition: 0.4s;
  background-color: rgb(177, 72, 89);
}

.btn:hover {
  background-color: rgb(141, 53, 68);
}

.input-group-text {
  padding-left: 15px;
  padding-right: 15px;
}
</style>
