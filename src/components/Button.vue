<template>
    <button class="button-claim">
        <div class="button-claim__text" :class="{ 'button-claim__text--large': large }">
            <slot></slot>
        </div>
    </button>
</template>
<script setup>
const props = defineProps({
    large: { type: Boolean, default: false }
})
</script>
<style scoped>
.button-claim__text {
    text-transform: uppercase;
    color: #FFF;
    text-align: center;
    text-shadow: 0px 0.5px 0px #1F1F1F;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: var(--Button-stroke, #1F1F1F);
    font-family: "Movavi Grotesque";
    font-size: 14px;
    font-style: normal;
    font-weight: 900;
    text-transform: uppercase;
    margin: auto;
}

.button-claim {
    display: flex;
    outline: none;
    border: none;
    height: 40px;
    min-height: 30px;
    padding: 12px 25px;
    justify-content: center;
    align-items: center;
    gap: 4px;
    border-radius: 18px;
    background: linear-gradient(180deg, #48A9EC 0%, #2875B9 100%);
    box-shadow: 0px 2px 0px 0px #BEE3FF inset, 0px 1px 1px 0px rgba(0, 0, 0, 0.25), 0px -2px 0px 0px #155388 inset;
    position: relative;
    min-width: 134px;
}
.button-claim::before {
    content: "";
    position: absolute;
    top: 1px;
    right: 10px;
    background-image: url("../assets/ellipse.svg");
    background-repeat: no-repeat;
    background-size: cover;
    width: 8px;
    height: 5px;
}
.button-claim__text--large {
    font-size: 20px;
}
</style>