<script>
    export default {
        name: 'AppHeader',
    }
</script>

<template>
    <header class="py-3 px-5">
        <div class="container-fluid">
            <div class="row">
                <div class="col">
                    <div class="mycard d-flex align-items-center">
                        <img class="me-5" src="../assets/Yu-Gi-Oh!_(Logo).jpg" alt="Logo Yu-Gi-Oh">
                        <h1 class="text-decoration-underline">Yu-Gi-Oh Api</h1>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style scope lang="scss">
    .mycard {

        img {
            width: 300px;
        }
    }
    
</style>