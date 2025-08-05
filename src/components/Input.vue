<template>
    <input
        min="0"
        type="number"
        @input="changeAmount($event.target.value)"
        placeholder="Bitte eine Zahl eingeben …"
    /><br />
    <div class="btns">
        <button @click="convert()">Konvertieren 🌀</button>
        <button @click="favorite()">Zu Favoriten hinzufügen ⭐️</button>
    </div>
</template>

<script>
    export default {
        props: {
            changeAmount: {
                type: Function,
                required: true,
            },
            convert: {
                type: Function,
                required: true,
            },
            favorite: {
                type: Function,
                required: true,
            },
        },
    }
</script>

<style scoped>
    input {
        border-radius: 3px;
        border: 0;
        padding: 20px 25px;
        background: #fafafa;
        color: #333;
        outline: none;
        width: 500px;
        position: relative;
        top: -20px;
        font-size: 1.2em;
        margin: 10px;
    }

    button {
        position: relative;
        top: -20px;
        padding: 15px 25px;
        color: #fff;
        font-size: 1.2em;
        text-transform: uppercase;
        cursor: pointer;
        background: linear-gradient(339deg, #d87b09, #d00a84, #6e0284);
        border: none;
        border-radius: 3px;
        transition: all 0.3s ease-in-out;
    }

    button:hover {
        background: linear-gradient(339deg, #6e0284, #d00a84, #d87b09);
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        transform: scale(1.1);
    }

    .btns {
        display: flex;
        justify-content: center;
        margin-top: 20px;
        gap: 50px;
    }
</style>
