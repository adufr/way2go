<template>
  <div>
    <div class="container-fluid col-centered pl-1 pr-1">
      <h2 class="h2 mb-4 text-gray-900">
        Todo-list
      </h2>

      <div class="input-group">
        <input
          v-model.trim="newTodo"
          type="text"
          class="form-control search-input border-0"
          placeholder="Ajoutez une tâche..."
          @keyup.enter="addTodo()"
          autofocus
        >
        <div class="input-group-append">
          <button class="btn btn-primary" type="button">
            <i class="fas fa-plus fa-sm"></i>
          </button>
        </div>
      </div>

      <h5 class="h5 mt-4 mb-4 text-gray-800">
        Tâches à faire
        <span v-show="remaining">({{ remaining.length }})</span>
      </h5>

      <span
        v-show="!remaining.length"
        class="text-gray-600"
      >
        Vous n'avez aucune tâche à faire !
      </span>

      <ul class="list-group" v-show="todos.length">
        <div v-for="(todo, index) in remaining" :key="index" class="card mb-2 border-left-warning">
            <div class="card-body pt-1 pb-1 pr-0 text-left">
              <div class="row no-gutters align-items-center">
                <div class="col mr-2">
                  <div>{{ todo.task }}</div>
                </div>
                <div class="col-auto dropdown no-arrow">
                  <button class="btn btn-default pl-1 pr-2" @click="completed(todo)">
                    <span class="fa fa-check" />
                  </button>
                  <button class="btn btn-default pl-1 pr-2 dropdown-toggle"  type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                    <span class="fa fa-info-circle" />
                  </button>
                  <div class="dropdown-menu">
                    <a class="dropdown-item">Créé par Arthur</a>
                    <a class="dropdown-item">Le 29/03/19 à 14h20</a>
                  </div>
                  <button class="btn btn-default pl-1 pr-3" @click="removeTodo(todo)">
                    <span class="fa fa-trash" />
                  </button>
                </div>
              </div>
          </div>
        </div>
      </ul>

      <div v-if="complete.length">
        <h5 class="h5 mt-4 mb-4 text-gray-800">
          Tâches complétées ({{ complete.length }})
        </h5>

        <ul class="list-group" v-show="todos.length">
          <div v-for="(todo, index) in complete" :key="index" class="card mb-2 border-left-success">
              <div class="card-body pt-1 pb-1 pr-0 text-left">
                <div class="row no-gutters align-items-center">
                  <div class="col mr-2">
                    <div>{{ todo.task }}</div>
                  </div>
                  <div class="col-auto dropdown no-arrow">
                    <button class="btn btn-default pl-1 pr-2" @click="completed(todo)">
                      <span class="fa fa-times" />
                    </button>
                    <button class="btn btn-default pl-1 pr-2 dropdown-toggle"  type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                      <span class="fa fa-info-circle" />
                    </button>
                    <div class="dropdown-menu">
                      <a class="dropdown-item">Terminé par Arthur</a>
                      <a class="dropdown-item">Le 29/03/19 à 15h17</a>
                    </div>
                    <button class="btn btn-default pl-1 pr-3" @click="removeTodo(todo)">
                      <span class="fa fa-trash" />
                    </button>
                  </div>
                </div>
            </div>
          </div>
          <!-- <button class="btn btn-danger" @click="clearAllCompleted()">
            Clear
            <span class="fa fa-trash" />
          </button> -->
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data () {
    return {
      newTodo: '',
      todos: [
        { task: 'Acheter carte de Pékin', completed: false },
        { task: 'Réserver visite muraille', completed: false },
        { task: 'Imprimer billets de train', completed: true }
      ]
    }
  },
  computed: {
    complete (todo) {
      return this.todos.filter(this.isCompleted)
    },
    remaining (todo) {
      return this.todos.filter(this.inProgress)
    }
  },
  methods: {
    isCompleted (todo) {
      return todo.completed
    },
    inProgress (todo) {
      return !this.isCompleted(todo)
    },
    addTodo () {
      let text = this.newTodo.trim()
      this.todos.push({ task: text, completed: false })
      this.newTodo = ''
    },
    removeTodo (todoToRemove) {
      // this.todos.$remove(todo)
      // Vue.delete(this.todos, todo)
      // this.todos.splice(this.todos.indexOf(todo), 1)
      // this.todos.splice(this.todos.map(todo => todo.task).indexOf(todo.task), 1)
      this.todos = this.todos.filter(todo => {
        return todo.task !== todoToRemove.task
      })
    },
    completed (todo) {
      todo.completed = !todo.completed
    },
    clearAllCompleted () {
      this.todos = this.todos.filter(this.inProgress)
    }
  }
}
</script>

<style scoped>
.search-input {
  height: 40px;
  padding: 30px;
  padding: 15px;
  border-radius: 8px
}
</style>
