
<template>
    <div :class="columnClass">
        <div class="card project-card h-100">
            <img
                :src="image"
                class="card-img-top"
                :alt="alt"
            />

            <div class="card-body">
                <h5 class="card-title">
                    {{ title }}
                </h5>

                <p class="card-text">
                    {{ description }}
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    },
    image: {
        type: String,
        required: true
    },
    alt: {
        type: String,
        required: true
    },
    columnClass: {
        type: String,
        default: "col-md-6 col-lg-4"
    }
});
</script>
