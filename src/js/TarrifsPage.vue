<template>
    <div>
        <Nav />
        <Head />
        <Features />
    </div>
</template>

<script>

import Nav from "./components/Nav.vue"
import Head from "./components/Head.vue"
import Features from "./components/Features.vue";
export default {
    components: { Nav, Head, Features },
}
</script>

<style lang="scss"></style>