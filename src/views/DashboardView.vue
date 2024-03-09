<template>
    <header>
        <div class="wrapper">
            <HelloWorld msg="YOU DID IT!" />
            <h1>
                JOHN JOSEPH P. ASORO
                <h2>2nd Year BSIT</h2>
            </h1>
        </div>

    </header>

</template>

<script>
export default {

}
</script>

<style scoped>
@media (min-width: 1024px) {
    header {
        display: flex;
        place-items: center;
        padding-right: calc(var(--section-gap) / 2);
    }
}
</style>