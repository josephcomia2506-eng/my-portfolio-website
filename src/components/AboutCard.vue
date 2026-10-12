
<template>
    <div class="col-md-4">
        <div class="about-card">
            <i class="bi" :class="icon"></i>

            <h4>{{ title }}</h4>

            <p>{{ description }}</p>
        </div>
    </div>
</template>

<script setup>
defineProps({
    icon: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    }
});
</script>
