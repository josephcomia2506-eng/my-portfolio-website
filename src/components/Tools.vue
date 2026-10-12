
<template>
    <section id="tools" class="py-5">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="section-title">
                    Tools & Technologies
                </h2>

                <p class="section-description">
                    Technologies and tools I use for developing responsive websites
                    and web applications.
                </p>
            </div>

            <div class="row g-5">
                <div
                    v-for="(category, index) in toolCategories"
                    :key="index"
                    class="col-lg-4"
                >
                    <h3 class="text-center mb-4">
                        {{ category.category }}
                    </h3>

                    <div class="row g-4 text-center">
                        <div
                            v-for="tool in category.tools"
                            :key="tool.name"
                            class="col-6"
                        >
                            <img
                                :src="tool.image"
                                class="tool-icon"
                                :alt="tool.name"
                            />

                            <p>{{ tool.name }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import toolCategories from "../data/tools.json";
</script>
