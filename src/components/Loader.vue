<template>
    <div class="loader">
        <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 16 16"
        >
            <path
                fill-rule="evenodd"
                d="M8 3a5 5 0 1 0 4.546 2.914.5.5 0 0 1 .908-.417A6 6 0 1 1 8 2v1z"
            />
            <path
                d="M8 4.466V.534a.25.25 0 0 1 .41-.192l2.36 1.966c.12.1.12.284 0 .384L8.41 4.658A.25.25 0 0 1 8 4.466z"
            />
        </svg>
        <div class="text">
            Caricamento
        </div>
    </div>
</template>

<script>
export default {
    name: "Loader",
};
</script>

<style scoped lang="scss">
.loader {
    position: fixed;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    background: rgba(0,0,0,.5);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    color: #fff;

    svg {
        width: 50%;
        height: 50%;
        fill: #fff;
        animation: loadSpinner 2s infinite linear;
    }

    @keyframes loadSpinner {
        to {
            transform: rotate(360deg);
        }       
    }

    .text {
        font-size: 2rem;
    }
}
</style>
