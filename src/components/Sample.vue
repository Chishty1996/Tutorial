<template>
  <div class="list row">

    <div class="col-md-6">
      <h4>Tutorials List</h4>
      <ul class="list-group">
        <li class="list-group-item"
            v-for="(tutorial, index) in tutorials"
            :key="index"
            @click="setActiveTutorial(tutorial, index)"
        >
          {{ tutorial.title }}
          <button @click="update(tutorial.id)">Delete</button>
        </li>
      </ul>
    </div>

<!--    <div @click="update" class="col-md-6">
      <div class="card-body">
        <br>
        <h4>Tutorial Details</h4>
        <div v-if="tutorials" v-html="tutorial.title">
        </div>
        <div>
          <label><strong>Description:</strong></label>description
        </div>
        <div>
          <label><strong>Status:</strong></label>published
        </div>
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

          <button class="btn btn-success" @click="update">Update</button>
        </div>
      </div>
    </div>-->
  </div>
</template>

<script>
//import TutorialDataService from "@/services/TutorialDataService";
export default {


  name: "sample",
  props: {
    tutorials: {
      type: [Array,Object],
    }
  },
  methods:
      {
        update(id) {
          this.$emit('removeTutorial', id)
          console.log(id);
        },

        setActiveTutorial(tutorial, index) {
          this.currentTutorial = tutorial;
          this.currentIndex = tutorial ? index : -1;
        },

        /*removeTutorial(id) {
          console.log(id);

          TutorialDataService.delete(id)
              .then(response => {
                console.log(response.data);
                this.$router.push({ name: "tutorials" });
              })
              .catch(e => {
                console.log(e);
              });
        },*/
      }
}

</script>

<style scoped>

</style>