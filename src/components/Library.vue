<template>
    <ul v-if="data !== null">
        <li
            v-for="(element, index) in data"
            :key="`album-${index}`"
        >
            <Card
                :img="element.poster"
                :title="element.title"
                :author="element.author"
                :year="element.year"
                :category="element.genre"
            />
        </li>
    </ul>
    <Loader v-else />
</template>

<script>
import Card from '@/components/Card.vue';
import Loader from '@/components/Loader.vue';

export default {
    name: 'Library',
    components: {
        Card,
        Loader,
    },
    props: {
        data: Array,
    },
}
</script>

<style scoped lang="scss">
ul {
    width: 100%;
    padding: 2rem;
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    li {
        width: calc(100% / 8);
        padding: 1rem;
    }
}

</style>