<template>
    <div>
        <img src="../assets/logo.png" alt="Logo">
    </div>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
@import '../styles/vars.scss';

div {
    background: $main-bg;

    img {
        height: 100px;
        padding: 1rem 1.5rem;
    }
}

</style>