<template>
  <div class="submit-form">
    <h4>Enter Tutorial Details</h4>
    <div v-if="!submitted">
      <div class="form-group">
        <label for="title">Title</label>
        <input
            type="text"
            class="form-control"
            id="title"
            required
            v-model="tutorial.title"
            name="title"
            placeholder="Enter Title"
        />
      </div>
      <div class="form-group">
        <label for="description">Description</label>
        <input
            class="form-control"
            id="description"
            required
            v-model="tutorial.description"
            name="description"
            placeholder="Enter Description"
        />
      </div>

      <button @click="saveTutorial" class="btn btn-success">Submit</button>
    </div>

    <div v-else >
      <h4>You submitted successfully!</h4>
      <button class="btn btn-success"  @click="newTutorial">RESET</button>
    </div>
  </div>
</template>

<script>
import TutorialDataService from "../services/TutorialDataService";

export default {
  name: "add-tutorial",
  data() {
    return {
      tutorial: {
        id: null,
        title: "",
        description: "",
        published: false
      },
      submitted: false
    };
  },
  methods: {
    saveTutorial() {
      var data = {
        title: this.tutorial.title,
        description: this.tutorial.description
      };
      console.log("Button Successful")
      TutorialDataService.create(data)
          .then(response => {
            this.tutorial.id = response.data.id;
            console.log(response.data);
            console.log(this.tutorial.title);
            console.log(this.tutorial.description);
            this.submitted = true;
          })
          .catch(e => {
            console.log(e);
          });
    },

    newTutorial() {
      this.submitted = false;
      //this.tutorial = {}
      console.log("action has been performed ")
    }
  }
};
</script>

<style>
.submit-form {
  max-width: 300px;
  margin: auto;
}
.form-group{
  margin-top: 15px;
}
.btn{
  margin-top: 20px;
}
</style>