<template>
  <div class="list row">

    <div class="col-md-6">
      <div>
        <br>
        <h4>Tutorial Details</h4>
        <div>
          <label><strong>Title:</strong></label>title
        </div>
        <div>
          <label><strong>Description:</strong></label>description
        </div>
        <div>
          <label><strong>Status:</strong></label>published
        </div>

        <button class="btn btn-primary">
          Update
        </button>
        <button class="button btn btn-danger">
          Delete
        </button>
      </div>

      <div class="submit">
        <div>
          <h4>Update Tutorial Form</h4>
          <div class="form-group">
            <label><strong>Title</strong></label>
            <input
                type="text"
                class="form-control"
                id="title"
                name="title"
            />
          </div>

          <div class="form-group">
            <label><strong>Description</strong></label>
            <input
                class="form-control"
                id="description"
                name="description"
            />
          </div>

          <button class="btn btn-success">Update</button>
        </div>
      </div>
    </div>

<!--    <div class="col-md-6">
      <div v-if="currentTutorial">
        <br>
        <h4>Tutorial Details</h4>
        <div>
          <label><strong>Title:</strong></label> {{ currentTutorial.title }}
        </div>
        <div>
          <label><strong>Description:</strong></label> {{ currentTutorial.description }}
        </div>
        <div>
          <label><strong>Status:</strong></label> {{ currentTutorial.published}}
        </div>

        <button class="btn btn-primary" @click="updateActiveTutorial(currentTutorial)">
          Update
        </button>
        <button class="button btn btn-danger" @click="removeTutorial(currentTutorial.id)">
          Delete
        </button>
      </div>
      <div v-else>
        <br />
        <p>Please click on a Tutorial...</p>
      </div>

      <div class="submit">
        <div v-if="updatepressed">
          <h4>Update Tutorial Form</h4>
          <div class="form-group">
            <label for="title"><strong>Title</strong></label>
            <input
                type="text"
                class="form-control"
                id="title"
                required
                v-model="updatepressed.title"
                name="title"
            />
          </div>

          <div class="form-group">
            <label for="description"><strong>Description</strong></label>
            <input
                class="form-control"
                id="description"
                required
                v-model="updatepressed.description"
                name="description"
            />
          </div>

          <button @click="updateTutorial" class="btn btn-success">Update</button>
        </div>
      </div>
    </div>-->
  </div>
</template>

<script>
/*import TutorialDataService from "../services/TutorialDataService";
export default {
  name: "tutorials-list",
  data() {
    return {
      tutorials: [],
      updatepressed: null,
      };
  },
  methods: {
    retrieveTutorials() {
      TutorialDataService.getAll()
          .then(response => {
            this.tutorials = response.data.data;
            console.log(response.data);
          })
          .catch(e => {
            console.log(e);
          });
    },

    refreshList() {
      this.retrieveTutorials();
      this.currentTutorial = null;
      this.currentIndex = -1;
    },

    tutorialSelected(tutorial, index) {
      this.currentTutorial = tutorial;
      this.currentIndex = tutorial ? index : -1;
    },

    removeTutorial(id) {
      console.log(id);

      TutorialDataService.delete(id)
          .then(response => {
            console.log(response.data);
            this.$router.push({ name: "tutorials" });
          })
          .catch(e => {
            console.log(e);
          });
    },

    updateActiveTutorial(data){
      this.updatepressed = data
      console.log("Update tutorial now!");
    },
    updateTutorial() {
      console.log("data");
      TutorialDataService.update(this.updatepressed.id, this.updatepressed)
          .then(response => {
            console.log(response.data);
            console.log("Tutorial updated successfully");
          })
          .catch(e => {
            console.log(e);
          });
    },

    searchTitle() {
      TutorialDataService.findByTitle(this.title)
          .then(response => {
            this.tutorials = response.data;
            this.setActiveTutorial(null);
            console.log(response.data);
          })
          .catch(e => {
            console.log(e);
          });
    }
  },
  mounted() {
    this.retrieveTutorials();
  }
};*/
</script>

<style>
.list {
  text-align: left;
  max-width: 750px;
  margin: auto;
}

.btn-danger{
  margin-left: 20px;
}

.submit{
  padding-top: 30px;
  margin-left: 0px !important;
}

.btn{
  margin-top: 20px;
}

.form-control{
  border-color: #42b983;
}

</style>