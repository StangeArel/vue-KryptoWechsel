<template>
    <h2>⭐️ Optionen in Favoriten</h2>
    <div
        @click="getFromFavs(index)"
        v-for="(element, index) in favs"
        :key="index"
        className="fav"
    >
        <span>{{ element.from }}</span>
        <span>{{ element.to }}</span>
    </div>
</template>

<script>
    export default {
        props: {
            favs: {
                type: Array,
                required: true,
            },
        },

        getFromFavs: {
            type: Function,
            required: true,
        },
    }
</script>

<style scoped>
    h2 {
        text-align: center;
        color: #10ed1f;
        font-size: 2em;
        margin-top: 50px;
        font-weight: bold;
        font-family: 'Montserrat', cursive !important;
    }

    .fav {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 300px;
        margin-top: 20px;
        font-size: 1.2em;
        color: #e70a9a;
        text-shadow:
            0 0 8px #e70a9a,
            0 0 15px #ff00ff,
            0 0 20px #ff69b4;
        transition: all 0.5s ease;
    }

    span {
        padding: 10px 15px;
        background: #8c00ff;
        border-radius: 15px 50px 15px 50px;
        color: #fff;
    }

    .fav:hover {
        opacity: 0.6;
        cursor: pointer;
        transform: scale(1.1);
    }
</style>
