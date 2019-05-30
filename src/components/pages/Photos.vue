<template>
  <div>
    <div class="container-fluid col-centered pl-1 pr-1">
      <h2 class="h2 mb-4 text-gray-900">
        Album photo
      </h2>

      <p class="text-gray-600 mb-5">
        Rajoutez ici toutes les photos de votre voyage, et choisissez avec qui vous souhaitez les partager !
      </p>

      <div class="card shadow mb-4">
        <a href="#collapse2" class="d-block card-header py-3" data-toggle="collapse" role="button" aria-expanded="true" aria-controls="collapse2">
          <h6 class="m-0 font-weight-bold text-primary text-left">Rizières (3)</h6>
        </a>
        <div class="collapse show" id="collapse2">
          <div class="card-body">
            <img src="../../assets/chine4.jpg" class="img-fluid mb-3" alt="Photo rizière">
            <img src="../../assets/chine5.jpeg" class="img-fluid mb-3" alt="Photo rizière">
            <img src="../../assets/chine6.jpeg" class="img-fluid mb-3" alt="Photo rizière">
          </div>
        </div>
      </div>

      <div class="card shadow mb-4">
        <a href="#collapseCardExample" class="d-block card-header py-3" data-toggle="collapse" role="button" aria-expanded="true" aria-controls="collapseCardExample">
          <h6 class="m-0 font-weight-bold text-primary text-left">Grande Muraille (3)</h6>
        </a>
        <div class="collapse show" id="collapseCardExample">
          <div class="card-body">
            <img src="../../assets/chine1.jpg" class="img-fluid mb-3" alt="Photo de la grande muraille">
            <img src="../../assets/chine2.jpg" class="img-fluid mb-3" alt="Photo de la grande muraille">
            <img src="../../assets/chine3.jpg" class="img-fluid mb-3" alt="Photo de la grande muraille">
          </div>
        </div>
      </div>

      <div class="card shadow mb-4">
        <a href="#collapse3" class="d-block card-header py-3" data-toggle="collapse" role="button" aria-expanded="true" aria-controls="collapse3">
          <h6 class="m-0 font-weight-bold text-primary text-left">Centre ville de Pékin (4)</h6>
        </a>
        <div class="collapse show" id="collapse3">
          <div class="card-body">
            <img src="../../assets/chine7.jpeg" class="img-fluid mb-3" alt="Photo centre pékin">
            <img src="../../assets/chine8.jpeg" class="img-fluid mb-3" alt="Photo centre pékin">
            <img src="../../assets/chine9.jpeg" class="img-fluid mb-3" alt="Photo centre pékin">
            <img src="../../assets/chine10.jpeg" class="img-fluid mb-3" alt="Photo centre pékin">
          </div>
        </div>
      </div>

      <div class="card shadow mb-4">
        <a href="#collapse4" class="d-block card-header py-3" data-toggle="collapse" role="button" aria-expanded="true" aria-controls="collapse4">
          <h6 class="m-0 font-weight-bold text-primary text-left">Arbres chinois (2)</h6>
        </a>
        <div class="collapse show" id="collapse4">
          <div class="card-body">
            <img src="../../assets/chine11.jpeg" class="img-fluid mb-3" alt="Arbre">
            <img src="../../assets/chine12.jpeg" class="img-fluid mb-3" alt="Arbre">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Photos'
}
</script>

<style scoped>
</style>
