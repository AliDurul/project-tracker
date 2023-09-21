<template>
  <div class="home">
    <div v-if="projects.length">
      <div v-for="project in projects" :key="project.id">
        <SingleProject
          @delete="hanldeDelete"
          @complete="handleComplete"
          :project="project"
        />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import SingleProject from "@/components/SingleProject";

export default {
  name: "HomeView",
  components: {
    SingleProject,
  },
  data() {
    return {
      projects: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/projects")
      .then((res) => res.json())
      .then((data) => (this.projects = data))
      .catch((err) => console.log(err.message));
  },
  methods: {
    hanldeDelete(id) {
      this.projects = this.projects.filter((project) => project.id !== id);
    },
    handleComplete(id) {
     this.projects.map((project) => {
        if (project.id === id) {
          project.complete = !project.complete;
        }
      });
    },
  },
};
</script>
