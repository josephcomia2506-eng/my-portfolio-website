
<template>
    <!-- ================= PROJECTS ================= -->
    <section id="projects" class="py-5">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="section-title">My Projects</h2>

                <p class="section-description">
                    Here are some of the projects I have completed and will continue
                    improving throughout my web development journey.
                </p>
            </div>

            <div class="row g-4">
			    <ProjectCard
			        v-for="(project, index) in projects"
			        :key="project.title"
			        :title="project.title"
			        :description="project.description"
			        :image="project.image"
			        :alt="project.alt"
			        :column-class="
			            index === projects.length - 1
			                ? 'col-lg-6 mx-auto'
			                : 'col-md-6 col-lg-4'
			        "
			    />
			</div>
        </div>
    </section>
</template>

<script setup>
import projects from "../data/projects.json";
import ProjectCard from "./ProjectCard.vue";
</script>
