<template>
    <div id="app">
        <header>
            <Header />
        </header>

        <main>
            <Library />
        </main>
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Library from '@/components/Library.vue';

export default {
    name: "App",
    components: {
        Header,
        Library
    },
};
</script>

<style lang="scss">
@import './styles/generals';
@import './styles/vars';

#app {
    background: $secondary-bg;
    min-height: 100vh;
    display: flex;
    flex-direction: column;

    header {
        flex-shrink: 0;
    }

    main {
        flex-grow: 1;
        display: flex;
        align-items: center;
    }
}
</style>
