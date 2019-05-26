<template>
  <div class="roboto">
    <div id="wrapper">
      <!-- ============================== -->
      <!-- == SIDEBAR =================== -->
      <!-- ============================== -->

      <ul
        id="accordionSidebar"
        class="navbar-nav bg-gradient-primary sidebar sidebar-dark accordion"
      >
        <!-- Sidebar - Brand -->
        <a
          class="sidebar-brand d-flex align-items-center"
          href="/#/dashboard?page=dashboard"
        >
          <div class="sidebar-brand-icon text-left ml-3 mr-3">
            <img
              class="img-fluid"
              style="width: 2.5rem"
              src="../assets/logo-white.png"
              alt="Logo"
            >
          </div>
          <div class="sidebar-brand-text">Way2Go</div>
        </a>

        <hr class="sidebar-divider my-0">

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'dashboard' } ]"
            class="nav-link"
            href="/#/dashboard?page=dashboard"
          >
            <i
              class="fas fa-fw fa-tachometer-alt"
              :class="['here', { active: page === 'dashboard' } ]"
            />
            <span>Tableau de bord</span>
          </a>
        </li>

        <hr class="sidebar-divider">

        <div class="sidebar-heading">
          Planification
        </div>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'groupe' } ]"
            class="nav-link"
            href="/#/dashboard?page=groupe"
          >
            <i
              class="fas fa-fw fa-users"
              :class="['here', { active: page === 'groupe' } ]"
            />
            <span>Groupe</span></a>
        </li>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'todo' } ]"
            class="nav-link"
            href="/#/dashboard?page=todo"
          >
            <i
              class="fas fa-fw fa-list"
              :class="['here', { active: page === 'todo' } ]"
            />
            <span>To-do list</span></a>
        </li>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'planning' } ]"
            class="nav-link"
            href="/#/dashboard?page=planning"
          >
            <i
              class="fas fa-fw fa-calendar"
              :class="['here', { active: page === 'planning' } ]"
            />
            <span>Planning</span></a>
        </li>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'budget' } ]"
            class="nav-link"
            href="/#/dashboard?page=budget"
          >
            <i
              class="fas fa-fw fa-credit-card"
              :class="['here', { active: page === 'budget' } ]"
            />
            <span>Budget</span></a>
        </li>

        <hr class="sidebar-divider">

        <div class="sidebar-heading">
          Divers
        </div>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'notes' } ]"
            class="nav-link"
            href="/#/dashboard?page=notes"
          >
            <i
              class="fas fa-fw fa-sticky-note"
              :class="['here', { active: page === 'notes' } ]"
            />
            <span>Notes</span></a>
        </li>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'conversation' } ]"
            class="nav-link"
            href="/#/dashboard?page=conversation"
          >
            <i
              class="fas fa-fw fa-comments"
              :class="['here', { active: page === 'conversation' } ]"
            />
            <span>Conversation</span></a>
        </li>

        <hr class="sidebar-divider">

        <div class="sidebar-heading">
          Autres
        </div>

        <li class="nav-item">
          <a
            :class="['here', { active: page === 'settings' } ]"
            class="nav-link"
            href="/#/dashboard?page=settings"
          >
            <i
              class="fas fa-fw fa-cogs"
              :class="['here', { active: page === 'settings' } ]"
            />
            <span>Paramètres</span></a>
        </li>

        <hr class="sidebar-divider">

        <!-- Sidebar Toggler (Sidebar) -->
        <div class="text-center d-none d-md-inline">
          <button
            id="sidebarToggle"
            class="rounded-circle border-0"
            @click="toggleSidebar"
          />
        </div>
      </ul>

      <div
        id="content-wrapper"
        class="d-flex flex-column"
      >
        <!-- ============================== -->
        <!-- == NAVBAR ==================== -->
        <!-- ============================== -->

        <nav class="navbar navbar-expand navbar-light bg-white topbar mb-4 static-top shadow">
          <!-- Sidebar Toggle (Topbar) -->
          <button
            id="sidebarToggleTop"
            class="btn btn-link d-md-none rounded-circle mr-3"
            style="color: #b14859"
            @click="toggleSidebar"
          >
            <i class="fa fa-bars" />
          </button>

          <!-- Topbar Navbar -->
          <ul class="navbar-nav ml-auto">
            <!-- Nav Item - Alerts -->
            <li class="nav-item dropdown no-arrow mx-1">
              <a
                id="alertsDropdown"
                class="nav-link dropdown-toggle"
                href="#"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                <i class="fas fa-bell fa-fw" />
                <!-- Counter - Alerts -->
                <span class="badge badge-danger badge-counter">2</span>
              </a>
              <!-- Dropdown - Alerts -->
              <div
                class="dropdown-list dropdown-menu dropdown-menu-right shadow animated--grow-in"
                aria-labelledby="alertsDropdown"
              >
                <h6 class="dropdown-header">
                  Notifications
                </h6>

                <div>
                  <a class="dropdown-item d-flex align-items-center pl-2 pr-2">
                    <div class="mr-2">
                      <div class="icon-circle bg-primary">
                        <i class="fas fa-file-alt text-white" />
                      </div>
                    </div>
                    <div>
                      <div class="font-weight-bold text-gray-700">Chine : Départ dans 7 jours !</div>
                      <span class="small text-gray-600">Plus qu'une semaine avant votre départ ! Vérifiez que vous n'avez rien oublié dans votre valise...</span>
                    </div>
                  </a>

                  <a class="dropdown-item d-flex align-items-center pl-2 pr-2">
                    <div class="mr-2">
                      <div class="icon-circle bg-primary">
                        <i class="fas fa-file-alt text-white" />
                      </div>
                    </div>
                    <div>
                      <div class="font-weight-bold text-gray-700">Canada : Billets d'avion</div>
                      <span class="small text-gray-600"><b>Thomas</b> viens d'indiquer qu'il a acheté son billet d'avion ! Avez-vous pris le votre ?</span>
                    </div>
                  </a>

                  <a class="dropdown-item text-center small text-gray-500">Tout marquer comme "lu"</a>
                </div>

                <!-- <div class="text-center text-gray-700 mb-3 mt-3">
                  <span>Aucune notification !</span>
                </div> -->
              </div>
            </li>

            <!-- Nav Item - Messages -->
            <li class="nav-item dropdown no-arrow mx-1">
              <a
                id="messagesDropdown"
                class="nav-link dropdown-toggle"
                href="#"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                <i class="fas fa-envelope fa-fw" />
                <!-- Counter - Messages -->
                <span class="badge badge-danger badge-counter">2</span>
              </a>
              <!-- Dropdown - Messages -->
              <div
                class="dropdown-list dropdown-menu dropdown-menu-right shadow animated--grow-in"
                aria-labelledby="messagesDropdown"
              >
                <h6 class="dropdown-header">
                  Messages
                </h6>

                <div>
                  <a class="dropdown-item d-flex align-items-center pl-2 pr-2">
                    <div class="mr-2">
                      <div class="icon-circle bg-primary">
                        <i class="fas fa-user text-white" />
                      </div>
                    </div>
                    <div>
                      <div class="font-weight-bold text-gray-700">Alexandre</div>
                      <span class="small text-gray-600">Est-ce que tu as pensé au taxi pour aller à l'aéroport ou bien tu veux...</span>
                    </div>
                  </a>

                  <a class="dropdown-item d-flex align-items-center pl-2 pr-2">
                    <div class="mr-2">
                      <div class="icon-circle bg-primary">
                        <i class="fas fa-users text-white" />
                      </div>
                    </div>
                    <div>
                      <div class="font-weight-bold text-gray-700">Canada</div>
                      <span class="small text-gray-600"><i>Vous avez 17 messages non-lus</i></span>
                    </div>
                  </a>

                  <a class="dropdown-item text-center small text-gray-500">Tout marquer comme "lu"</a>
                </div>

                <!-- <div class="text-center text-gray-700 mb-3 mt-3">
                  <span>Aucune notification !</span>
                </div> -->
              </div>
            </li>

            <div class="topbar-divider d-none d-sm-block" />

            <!-- Nav Item - User Information -->
            <li class="nav-item dropdown no-arrow">
              <a
                id="userDropdown"
                class="nav-link dropdown-toggle"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                <span class="mr-2 d-none d-lg-inline text-gray-600 small">John Doe</span>
                <img
                  class="img-profile rounded-circle"
                  src="https://www.shareicon.net/data/128x128/2016/05/24/770121_man_512x512.png"
                >
              </a>
              <!-- Dropdown - User Information -->
              <div
                class="dropdown-menu dropdown-menu-right shadow animated--grow-in"
                aria-labelledby="userDropdown"
              >
                <a
                  class="dropdown-item text-gray-500"
                  href="/#/dashboard?page=conversation"
                >
                  <i class="fas fa-user fa-sm fa-fw mr-2" />
                  Mon profil
                </a>
                <a
                  class="dropdown-item text-gray-500"
                  href="/#/dashboard?page=settings"
                >
                  <i class="fas fa-cogs fa-sm fa-fw mr-2 " />
                  Paramètres
                </a>
                <div class="dropdown-divider" />
                <a
                  class="dropdown-item text-gray-500"
                  data-toggle="modal"
                  data-target="#logoutModal"
                  @click="logout"
                >
                  <i class="fas fa-sign-out-alt fa-sm fa-fw mr-2" />
                  Déconnexion
                </a>
              </div>
            </li>
          </ul>
        </nav>

        <!-- ============================== -->
        <!-- == PAGES ===================== -->
        <!-- ============================== -->

        <div id="content">
          <div class="container-fluid">
            <Main v-show="page === 'dashboard'" />
            <Groupe v-show="page === 'groupe'" />
            <Todo v-show="page === 'todo'" />
            <Planning v-show="page === 'planning'" />
            <Budget v-show="page === 'budget'" />
            <Notes v-show="page === 'notes'" />
            <Conversation v-show="page === 'conversation'" />
            <Settings v-show="page === 'settings'" />
          </div>
        </div>

        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import router from '../router'

import Footer from '../components/Footer.vue'

import Main from '../components/pages/Main.vue'
import Groupe from '../components/pages/Groupe.vue'
import Todo from '../components/pages/Todo.vue'
import Planning from '../components/pages/Planning.vue'
import Budget from '../components/pages/Budget.vue'
import Notes from '../components/pages/Notes.vue'
import Conversation from '../components/pages/Conversation.vue'
import Settings from '../components/pages/Settings.vue'

export default {
  name: 'Dashboard',
  components: {
    Footer,
    Main,
    Groupe,
    Todo,
    Planning,
    Budget,
    Notes,
    Conversation,
    Settings
  },
  data () {
    return {
      page: this.$route.query.page
    }
  },
  watch: {
    '$route' (to, from) {
      this.page = to.query.page
    }
  },
  methods: {
    logout: function () {
      router.push('/')
    },
    toggleSidebar: function () {
      document.querySelector('body').classList.toggle('sidebar-toggled')
      document.querySelector('.sidebar').classList.toggle('toggled')
    }
  }
}
</script>

<style scoped>
.here.active {
  color: white !important;
}

.roboto {
  font-family: 'Roboto', sans-serif !important;
}
</style>
