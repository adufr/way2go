<template>
  <div class="container-fluid pl-0 pr-0">
    <!-- Page heading -->
    <div class="d-sm-flex align-items-center justify-content-between mb-4">
      <h1 class="h3 mb-2 text-gray-800">
        Tableau de bord : Chine
      </h1>
      <h3 class="h5 mb-0 text-gray-500">
        Départ dans 7 jours !
      </h3>
    </div>

    <div class="row">
      <div class="col-xl-3 col-md-6 mb-4">
        <div class="card border-left-info shadow h-100 py-0">
          <div class="card-body">
            <div class="row no-gutters align-items-center">
              <div class="col mr-2 text-left">
                <div class="text-xs font-weight-bold text-info text-uppercase mb-1">
                  ÉTAT DE LA PLANIFICATION
                </div>
                <div class="row no-gutters align-items-center">
                  <div class="col-auto">
                    <div class="h5 mb-0 mr-3 font-weight-bold text-gray-800">
                      30%
                    </div>
                  </div>
                  <div class="col">
                    <div class="progress progress-sm mr-2">
                      <div
                        class="progress-bar bg-info"
                        role="progressbar"
                        style="width: 30%"
                        aria-valuenow="30"
                        aria-valuemin="0"
                        aria-valuemax="100"
                      />
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-auto">
                <i class="fas fa-clipboard-list fa-2x text-gray-300" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-xl-3 col-md-6 mb-4">
        <div class="card border-left-warning shadow h-100 py-0">
          <div class="card-body">
            <div class="row no-gutters align-items-center">
              <div class="col mr-2 text-left">
                <div class="text-xs font-weight-bold text-warning text-uppercase mb-1">
                  TÂCHES RESTANTES
                </div>
                <div class="h5 mb-0 font-weight-bold text-gray-800">
                  17
                </div>
              </div>
              <div class="col-auto">
                <i class="fas fa-tasks fa-2x text-gray-300" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-xl-3 col-md-6 mb-4">
        <div class="card border-left-success shadow h-100 py-0">
          <div class="card-body">
            <div class="row no-gutters align-items-center">
              <div class="col mr-2 text-left">
                <div class="text-xs font-weight-bold text-success text-uppercase mb-1">
                  BUDGET (PAR PERSONNE)
                </div>
                <div class="h5 mb-0 font-weight-bold text-gray-800">
                  2550,00€
                </div>
              </div>
              <div class="col-auto">
                <i class="fas fa-euro-sign fa-2x text-gray-300" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Content Row -->
    <div class="row">
      <div class="col-xl-4 col-lg-5">
        <div class="card shadow mb-4">
          <!-- Card Header - Dropdown -->
          <div class="card-header py- d-flex flex-row align-items-center justify-content-between">
            <h6 class="m-0 font-weight-bold text-primary">Répartition du budget</h6>
            <div class="dropdown no-arrow">
              <a class="dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                <i class="fas fa-ellipsis-v fa-sm fa-fw text-gray-400"></i>
              </a>
              <div class="dropdown-menu dropdown-menu-right shadow animated--fade-in" aria-labelledby="dropdownMenuLink">
                <div class="dropdown-header">Affichage</div>
                <a class="dropdown-item" href="#">Une action</a>
                <a class="dropdown-item" href="#">Une autre action</a>
              </div>
            </div>
          </div>
          <!-- Card Body -->
          <div
            class="card-body pl-0 pr-0"
            style="width: xpx; margin: 0 auto"
          >
            <div class="chart-pie pt-2 pb-2">
              <pie-chart style="height: 210px; width: 210px" :data="chartData"></pie-chart>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PieChart from '../PieChart.js'

export default {
  name: 'Main',
  components: {
    PieChart
  },
  data () {
    return {
      chartData: {
        labels: ['Avion', 'Hôtel', 'Nourriture', 'Visites', 'Extras'],
        datasets: [
          {
            label: 'Répartition du budget',
            backgroundColor: ['#a341f4', '#E46651', '#019b41', '#e9ed25'],
            data: [600, 1000, 200, 250, 500]
          }
        ]
      }
    }
  }
}
</script>

<style scoped>
.img-fluid {
  max-height: 260px
}
</style>
