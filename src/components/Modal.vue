<template>
    <div class="modal" @click="handleClick">
        <div class="modal__content" @click.stop>
            <div class="modal__top">CONGRATULATIONS!</div>
            <div class="modal__bottom">
                <div class="modal-experience">
                    <div class="modal-experience__wrap">
                        <div class="modal-experience__item green">
                            <img class="modal-experience__img" src="../assets/img/mouse.png" alt="">
                        </div>
                        <span>+500xp</span>
                    </div>
                    <div class="modal-experience__wrap">
                        <div class="modal-experience__item purple">
                            <img class="modal-experience__img" src="../assets/img/mousef.png" alt="">
                        </div>
                        <span>+500xp</span>
                    </div>
                    <div class="modal-experience__wrap">
                        <div class="modal-experience__item blue">
                            <img class="modal-experience__img" src="../assets/img/mouses.png" alt="">
                        </div>
                        <span>+500xp</span>
                    </div>
                </div>
                <div class="modal__bonus">
                    <div class="modal__fan-bonus--title yellow">fan Bonus</div>
                    <div class="modal__fan-bonus--content">
                        <div class="modal__fan-bonus--item">
                            <img class="modal-experience__img" src="../assets/medal.svg" alt="">
                            <span>150</span>
                        </div>
                        <div class="modal__fan-bonus--item">
                            <span>5.5k</span> 
                        </div>
                    </div>
                </div>
                <div class="modal__bonus">
                    <div class="modal__fan-bonus--title blue">total reward</div>
                    <div class="modal__fan-bonus--content">
                        <div class="modal__fan-bonus--item tall">
                            <img class="modal-experience__img" src="../assets/medal.svg" alt="">
                            <span>399</span>
                        </div>
                        <div class="modal__fan-bonus--item">
                            <span>120.5k</span> 
                        </div>
                    </div>
                </div>
            </div>
            <Button @click="openCloseModal">ok</Button>
        </div>
    </div>
</template>
<script setup>
import { defineEmits } from 'vue';
import Button from './Button.vue';
const emit = defineEmits(['close']);
const handleClick = () => {
    emit('close', false);
};
const openCloseModal = () => {
    emit('close', false);
}
</script>
<style scoped>
.modal {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.85);
    z-index: 2;
    cursor: pointer;
    display: flex;
}

.modal__content {
    width: 318px;
    min-height: 295px;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px;
    padding: 0 21px;
}

.modal__top {
    width: 100%;
    color: #FFF;
    text-align: center;
    text-shadow: 0px 1px 0px #000;
    font-family: "Movavi Grotesque";
    font-size: 24px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
    text-transform: uppercase;
    background: linear-gradient(90deg, rgba(243, 194, 9, 0.00) 0%, #F3C209 24%, #F3C209 70%, rgba(243, 194, 9, 0.00) 100%);
}

.modal__bottom {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 24px;
}

.modal-experience {
    display: flex;
    gap: 12px;
    justify-content: space-between;
}

.modal-experience__item {
    width: 43px;
    height: 43px;
    border-radius: 8px;
    background: radial-gradient(196.11% 271.57% at 50% -171.57%, #336097 0%, #1D2948 100%);
    display: flex;
    overflow: hidden;
}

.modal-experience__item.green {
    border: 1px solid #88FF2A;
}

.modal-experience__item.purple {
    border: 1px solid #EA6BFF;
}

.modal-experience__item.blue {
    border: 1px solid #7CD0FF;
}

.modal-experience__wrap {
    display: flex;
    flex-direction: column;
    gap: 4px;
    align-items: center;
}

.modal-experience__wrap>span {
    color: #FFF;
    text-align: center;
    font-family: "Movavi Grotesque";
    font-size: 14px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
    text-transform: lowercase;
}

.modal__bonus {
    display: flex;
    flex-direction: column;
    width: 100%;
    gap: 4px;
}

.modal__fan-bonus--title {
    text-shadow: 0px 0.579px 0px #000;
    -webkit-text-stroke-width: 0.28973597288131714;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: "Changa One";
    font-size: 20px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    text-transform: uppercase;
    text-align: center;
}
.modal__fan-bonus--title.yellow {
    color: #F3C209;
}
.modal__fan-bonus--title.blue {
    color: #A8DEFD;
}

.modal__fan-bonus--content {
    display: flex;
    gap: 24px;
    padding: 4px 0;
    background: linear-gradient(90deg, rgba(32, 94, 170, 0.00) -8.33%, rgba(31, 89, 132, 0.50) 43.52%, rgba(31, 89, 132, 0.50) 63.78%, rgba(32, 94, 170, 0.00) 110.86%);
}

.modal__fan-bonus--item {
    width: calc(50% - 12px);
    display: flex;
    gap: 4px;
    align-items: center;
    justify-content: center;
    min-height: 32px;
}

.modal__fan-bonus--item.tall {
    min-height: 39px;
}

.modal__fan-bonus--item > span {
    color: #FFF;
    text-shadow: 0px 0.5px 0px rgba(0, 0, 0, 0.50);
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: var(--stroke-counter, #000);
    font-family: "Movavi Grotesque";
    font-size: 16px;
    font-style: normal;
    font-weight: 900;
    line-height: normal;
}
.modal-experience__img {
    width: 100%;
    max-width: 43px;
    object-fit: cover;
    margin: auto;
}
</style>