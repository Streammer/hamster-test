<template>
    <div class="games-released">
        <ReleasedList/>
    </div>
</template>
<script setup>
import { defineOptions } from 'vue';
import ReleasedList from './ReleasedList.vue';
defineOptions({ name: 'GamesReleased' });
</script>
<style scoped>
.games-released {
    min-width: 360px;
    display: flex;
    padding: 36px 19px 24px 19px;
    flex-direction: column;
    align-items: center;
    gap: 16px;
    background: linear-gradient(180deg, #2361A8 0%, #224378 132.67%);
    width: 100%;
    min-height: 640px;
}

.games-released__title {
    color: #FFF;
    text-align: center;
    font-size: 20px;
    font-style: normal;
    font-weight: 900;
    line-height: 16px;
    text-transform: uppercase;
}
</style>