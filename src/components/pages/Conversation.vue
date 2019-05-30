<template>
  <div>
    <div class="container-fluid col-centered pl-0 pr-0">
      <!-- <h2 class="h2 mb-4 text-gray-900">
        Chine (8 membres)
      </h2> -->

      <basic-vue-chat
        :title="'Groupe : Voyage Chine'"
        :initial-feed="feed"
      />

    </div>
  </div>
</template>

<script>
import BasicVueChat from 'basic-vue-chat'

export default {
  name: 'Conversation',
  components: {
    BasicVueChat
  },
  mounted () {
    document.querySelectorAll('input').forEach(input => {
      if (input.placeholder === 'Type message...') {
        input.placeholder = 'Envoyez un message...'
      }
    })

    document.querySelector('.input__button').textContent = 'Envoyer'
  },
  data () {
    return {
      feed: [
        {
          id: 3,
          author: 'Victoire',
          contents: "Plus qu'une semaine avant le départ, j'ai vraiment trop hâte!",
          date: '10:21:10'
        },
        {
          id: 2,
          author: 'Thomas',
          contents: 'Yes, vos valises sont prêtes ?',
          date: '10:29:10'
        },
        {
          id: 1,
          author: 'Alexandre',
          contents: "Moi c'est tout bon, j'aurais plus qu'à faire mon sac-à-dos",
          date: '11:12:15'
        },
        {
          id: 0,
          author: 'Me',
          contents: 'Le mien est déjà prêt !',
          date: '11:14:15'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
$primary:#b14859 !important;
$secondary:#b14859 !important;
$light-text-color: #f1f1f1 !important;
$light-bg: #272222 !important;
$dark-bg: #dddcdc !important;
$input-background-color: #eeeeee !important;
$header-color: #ffffff !important;
$window-height: 600px !important;
$window-width: 600px !important;
@import "../../../node_modules/basic-vue-chat/src/assets/scss/main.scss";

.window__header__container {
  background: #b14859 !important
}

.message__contents {
  text-align: left
}

.message__date {
  display: none !important;
}

div {
  border: none !important
}
</style>
