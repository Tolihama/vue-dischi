<template>
    <div class="card">
        <img :src="img" :alt="`Album ${title}`">
        <div class="infos">
            <h3 class="title">{{ title }}</h3>
            <h4 class="author">{{ author }}</h4>
            <h5 class="year">{{ year }}</h5>
            <h5 class="category">{{ category }}</h5>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        img: String,
        title: String,
        author: String,
        year: String,
        category: String,
    },
}
</script>

<style scoped lang="scss">
@import '../styles/vars.scss';

.card {
    padding: 1rem;
    height: 100%;
    background: $main-bg;
    text-align: center;
    

    img {
        width: 100%;
    }

    .title {
        text-transform: uppercase;
        padding: 1rem 0;
        font-size: 1.4rem;
        letter-spacing: 1px;
    }

    .author {
        font-size: 1.25rem;
    }

    .year,
    .category {
        font-size: 1rem;
    }

    .title,
    .category {
        color: $primary-text;
    }

    .author,
    .year {
        color: $secondary-text;
    }

    .author,
    .year,
    .category {
        padding: .25rem 0;
    }
}
</style>