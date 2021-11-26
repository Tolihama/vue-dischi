<template>
    <div id="app">
        <Header @optionSelected="genreFilter" :options="genresList" />
        <main>
            <Library :data="filteredAlbums" />
        </main>
    </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Library from "@/components/Library.vue";

import axios from "axios";

export default {
    name: "App",
    components: {
        Header,
        Library,
    },
    data() {
        return {
            albums: null,
            activeAlbumFilter: "All",
            genresList: [],
        };
    },
    computed: {
        filteredAlbums() {
            if (this.activeAlbumFilter === "All") {
                return this.albums;
            }

            return this.albums.filter(
                (e) => e.genre === this.activeAlbumFilter
            );
        },
    },
    created() {
        this.getData();
    },
    methods: {
        getData() {
            axios
                .get("https://flynn.boolean.careers/exercises/api/array/music")
                .then((result) => {
                    this.albums = result.data.response;
                    this.albums.forEach((album) => {
                        if (!this.genresList.includes(album.genre)) {
                            this.genresList.push(album.genre);
                        }
                    });
                })
                .catch((err) => console.log(err));
        },
        genreFilter(text) {
            this.activeAlbumFilter = text;
        },
    },
};
</script>

<style lang="scss">
@import "./styles/generals";
@import "./styles/vars";

#app {
    background: $secondary-bg;
    min-height: 100vh;
    display: flex;
    flex-direction: column;

    header {
        flex-shrink: 0;
    }

    main {
        display: flex;
    }
}
</style>
