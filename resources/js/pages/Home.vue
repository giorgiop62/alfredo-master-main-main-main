<script>
export default {
    name: "Home",
};
</script>

<template>
    <div class="container-fluid d-flex align-items-center justify-content-center">
        <img class="desktop" src="../assets/violinome.jpg" alt="">
        <img class="mobile" src="../assets/contact.jpg" alt="">
        <div>
            <h1>Alfredo Pumilia Composer</h1>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container-fluid {
    background-color: black;
    color: white;
    height: 100vh;
}

img {
    height: 100%;
    width: 70%;
}

.mobile {
    display: none;
}

@media (max-width: 767px) {
    h1 {
        display: none;
    }

    .desktop {
        display: none;
    }

    .mobile {
        display: block;
        width: 100%;
    }
}
</style>
