<template>
    <div>
        <!-- Nav -->
        <Nav />

        <!-- Content -->
        <slot />

    </div>
</template>

<script>
import Nav from './Nav.vue'
export default {
    name:'App-Master',
    components: {Nav},
}
</script>