
<template>
    <!-- ================= ABOUT ================= -->
    <section id="about" class="py-5">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 mx-auto text-center">

                    <h2 class="section-title">
                        About Me
                    </h2>

                    <p class="section-description">
                        I recently completed my Bachelor of Science in Information
                        Technology and continue improving my skills in web
                        development. My experience includes building responsive
                        websites, RESTful APIs, and full-stack web applications
                        using HTML, CSS, Bootstrap, JavaScript, PHP, Laravel,
                        MySQL, and modern development tools.
                    </p>

                    <div class="row mt-5">
					    <AboutCard
					        v-for="card in aboutCards"
					        :key="card.title"
					        :icon="card.icon"
					        :title="card.title"
					        :description="card.description"
					    />
					</div>

                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import aboutCards from "../data/about.json";
import AboutCard from "./AboutCard.vue";
</script>
