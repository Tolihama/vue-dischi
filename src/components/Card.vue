<template>
    <div class="card">
        <div class="card-img">
            <img :src="img" :alt="title">
        </div>
        <div class="card-text">
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
    height: 100%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    background: $main-bg;

    .card-img {
        height: 100%;
        
        img {
            display: block;
            width: 100%;
        }
    }

    .card-text {
        padding: 1.5rem 0 0;
        height: 100%;
        background: $main-bg;
        text-align: center;

        .title {
            text-transform: uppercase;
            padding: 0 0 1rem;
            font-size: 1.4rem;
            font-weight: 700;
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
            font-weight: 600;
        }
    }
}
</style>