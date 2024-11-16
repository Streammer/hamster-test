<template>
    <div class="released-list__wrapper">
        <div class="released-list__content">
            <div class="released-list">
                <div v-for="item in data" :key="item.id" class="released-list__item">
                    <div class="released-list__name">{{ item.name }}</div>
                    <div class="released-list__awards">
                        <span class="released-list__awards-title">REWARD</span>
                        <div v-if="item.reward.medals" class="released-list__points-values">
                            <img src="@/assets/medal.svg" alt="medal icon">
                            <span class="released-list__medals">{{ formatNumber(item.reward.medals) }}</span>
                        </div>
                        <span class="released-list__points">{{ formatNumber(item.reward.points) }}</span>
                        <span class="released-list__awards-title" :class="item.funBonus.medals ? 'orange' : 'red'">FUN
                            BONUS</span>
                        <div v-if="item.funBonus.medals" class="released-list__points-values">
                            <img src="@/assets/medal.svg" alt="medal icon">
                            <span class="released-list__medals">{{ formatNumber(item.funBonus.medals) }}</span>
                        </div>
                        <span class="released-list__points">{{ formatNumber(item.funBonus.points) }}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue'
const data = ref([
    { id: 1, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 2, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
    { id: 3, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
    { id: 4, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 5, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 6, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 7, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
    { id: 8, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
    { id: 9, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 10, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 11, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: 12, points: 500 } },
    { id: 12, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
    { id: 13, name: 'puzzle', reward: { medals: 200, points: 2500 }, funBonus: { medals: null, points: null } },
])
const formatNumber = (value) => {
    if (value < 1000) {
        return value;
    }
    else {
        const result = value / 1000;
        return Number.isInteger(result) ? result + 'k' : result.toFixed(1) + 'k';
    }
}
</script>
<style scoped>
.released-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-left: 41px;
    width: 100%;
}

.released-list__wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
    flex: 1 0 0;
    max-width: 322px;
    width: 100%;
    min-height: 155px;
    max-height: 440px;
    padding: 8px 4px;
    border-radius: 12px;
    border-right: 1px solid #3579B5;
    border-bottom: 1px solid #3579B5;
    border-left: 1px solid #3579B5;
    background: radial-gradient(51.09% 70.69% at 50% 52.89%, #3081B4 0%, #19488C 100%);
    box-shadow: 0px 4px 4.5px 0px rgba(0, 3, 6, 0.50) inset;
    overflow: hidden;
}

.released-list__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    overflow-y: auto;
    padding-right: 41px;
    box-sizing: content-box;
}

.released-list__item {
    width: 100%;
    display: flex;
    padding: 4px 24px;
    justify-content: flex-start;
    align-items: center;
    border-bottom: 1px solid rgba(168, 222, 253, 0.20);
}

.released-list__name {
    min-width: max-content;
    width: 20%;
    color: #FFF;
    text-shadow: 0px 0.579px 0px #000;
    -webkit-text-stroke-width: 0.28973597288131714;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: Lato;
    font-size: 8px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
    text-transform: uppercase;
    align-self: flex-end;
}

.released-list__reward,
.released-list__fun-bonus {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    align-self: stretch;
}

.released-list__reward>span,
.released-list__fun-bonus>span {
    display: flex;
    text-shadow: 0px 0.579px 0px #000;
    -webkit-text-stroke-width: 0.28973597288131714;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: Lato;
    font-size: 12px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
    text-transform: uppercase;
}

.released-list__reward>span {
    color: #FFF;
}

.released-list__awards {
    width: 80%;
    margin-left: auto;
    display: grid;
    grid-template-columns: minmax(max-content, 1fr) minmax(0, 1fr) minmax(0, 1fr);
    row-gap: 7px;
}

.released-list__points-values {
    display: flex;
    align-items: center;
    gap: 4px;
    justify-self: flex-start;
    padding-left: 14px;
}

.released-list__awards-title {
    color: #FFF;
    text-shadow: 0px 0.579px 0px #000;
    -webkit-text-stroke-width: 0.28973597288131714;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: Lato;
    font-size: 12px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
    text-transform: uppercase;
    white-space: nowrap;
}

.released-list__awards-title.orange {
    color: #F3C209;
}

.released-list__awards-title.red {
    color: #FF7957;
}

.released-list__medals,
.released-list__points {
    color: #FFF;
    text-shadow: 0px 0.5px 0px rgba(0, 0, 0, 0.50);
    -webkit-text-stroke-width: 0.5;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: "Movavi Grotesque";
    font-size: 12px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
}
.released-list__points {
    justify-self: flex-start;
    margin-left: auto;
}
</style>