<template>

  <div>
    <h2 style="text-align: center;">Welcome to Online tutorials!</h2>
    <br>
    <Sample :tutorials="tutorials" :key="tutorials.id" @removeTutorial="removeTutorial"></Sample>
<!--    <Sample :title="title" @titleChanged="titleChanged"></Sample>-->
  </div>

</template>
<script>
import Sample from "@/components/Sample";
import TutorialDataService from "@/services/TutorialDataService";
export default {
  components: {Sample},


  data() {
    return {
      tutorials: [],
      currentTutorial: null,
      currentIndex: -1,
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
  },
  mounted() {
    this.retrieveTutorials();
  },
};
</script>