<script setup lang="ts">
import ProjectsItem from '@/components/ProjectsItem.vue';

// Get project data from Github repositories
// user MarcTheDuck
function fetchGitHubProjects(username: string) {
  return fetch(`https://api.github.com/users/${username}/repos`)
    .then(response => response.json())
    .then(data => {
      
    });
}
  

</script>

<template>
  <main>
    <h1>My Projects</h1>
    <ProjectsItem
      title="Project Alpha"
      iconUrl="/assets/project-alpha-icon.png"
      description="A cutting-edge platform for collaborative work."
      link="https://example.com/project-alpha"
    />
  </main>
</template>
