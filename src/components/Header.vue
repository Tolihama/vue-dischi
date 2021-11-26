<template>
    <header>
        <div class="logo">
            <img src="../assets/logo.png" alt="Logo" />
        </div>
        <div class="select">
            <label for="Genre">Select Genre:</label>
            <select
                name="Genre"
                v-model="genreSelected"
                @change="$emit('optionSelected', genreSelected)"
            >
                <option value="All">All Genres</option>
                <option 
                    v-for="(genre, index) in options"
                    :key="`option-${index}`"
                    :value="genre"
                >
                    {{ genre }}
                </option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
    data() {
        return {
            genreSelected: "All",
        };
    },
    props: {
        options: Array,
    }
};
</script>

<style scoped lang="scss">
@import "../styles/vars.scss";

header {
    background: $main-bg;
    display: flex;
    align-items: center;

    .logo {
        padding: 1rem 1.5rem;
        flex-grow: 1;

        img {
            height: 50px;
        }
    }

    .select {
        margin-right: 50px;

        label {
            margin-right: 10px;
            color: $primary-text;
            font-size: 1rem;
            font-weight: 700;
        }

        select {
            padding: 10px 5px;
        }
    }
}
</style>
