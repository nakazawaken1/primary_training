<template>
    <Stage :status="status">
        <ImageBack1 style="position: absolute;top:0;left:0" />
        <section v-if="stage == 'start'" @click="stage = 'main'" class="clickable">
            <ImageTitle1 style="position: absolute;top:85px;left:130px" />
            <Animal name="shimauma" :x="0" :y="604" style="zoom:0.6;transform:scale(-1,1)" />
            <Animal name="buta" :x="238" :y="554" style="zoom:0.6;transform:scale(-1,1)" />
            <Animal name="usagi" :x="1450" :y="650" style="zoom:0.6" />
            <Animal name="lion" :x="1200" :y="604" style="zoom:0.6" />
            <ButtonStart style="position: absolute;top:405px;left:375px" :hover="hover" @pointerenter="hover = true"
                @pointerleave="hover = false" />
        </section>
        <section v-else-if="stage == 'main'">
            <Fukidashi style="margin-top:32px">からだのおおきいじゅんにクリックしよう！</Fukidashi>
            <Animal v-for="animal of animals" :key="animal.order" :x="animal.x" :y="animal.y" :name="animal.name"
                @hit="click(animal)" :clicked="animal.clicked" />
        </section>
        <section v-else @click="stage = 'start'" class="clickable">
            <img v-if="['clear', 'gameover'].includes(stage)" :src="svg(stage)" :alt="stage"
                style="position: absolute;top:-15px" />
            <footer style="zoom:50%;bottom:400px;position:absolute;display:flex">
                <Animal v-for="animal of sorted" :key="animal.order" :name="animal.name" :style="{position: 'relative', transform: stage == 'gameover' ? 'scale(1,-1)' : null}" />
            </footer>
            <ButtonRetry style="position:absolute;bottom:100px" />
        </section>
    </Stage>
</template>

<script lang="ts" setup>
const animals = [
    { x: 600, y: 230, name: 'zou', order: 1, clicked: false },
    { x: 0, y: 100, name: 'kaba', order: 2, clicked: false },
    { x: 360, y: 100, name: 'tora', order: 3, clicked: false },
    { x: 200, y: 280, name: 'saru', order: 4, clicked: false },
    { x: 800, y: 50, name: 'kame', order: 5, clicked: false },
];
const hover = ref(false);
const stage = ref('start');
const scoreMax = animals.length;
const score = ref(scoreMax);
const lifeMax = 3;
const life = ref(lifeMax);
const sorted = computed(() => [...animals].sort((a, b) => a.order - b.order));
const status = computed(() => stage.value == 'main' ? { score: score.value, scoreMax, life: life.value, lifeMax } : null)
const click = (animal: { clicked: boolean }) => {
    if (sorted.value.find(i => i == animal)?.clicked === true) return;
    const remains = sorted.value.filter(i => !i.clicked);
    if (remains[0] === animal) {
        animal.clicked = true;
        score.value--;
        if (remains.length <= 1) stage.value = 'clear';
    } else {
        life.value--;
        if (life.value <= 0) stage.value = 'gameover';
    }
}
watch(stage, value => {
    if (value == 'start') {
        score.value = scoreMax;
        life.value = lifeMax;
        animals.forEach(i => i.clicked = false);
    }
})
</script>

<style lang="scss" scoped>
section {
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
}

.clickable {
    cursor: pointer;
}
</style>