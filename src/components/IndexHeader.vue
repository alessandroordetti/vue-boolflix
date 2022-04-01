<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <nav class="navbar navbar-dark justify-content-between">
                        <img src="../assets/logo.png" alt="Netflix Logo">
                        <form class="form-inline d-flex">
                            <input class="form-control mx-3 mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                            <button class="btn btn-primary my-2 my-sm-0" type="submit">Search</button>
                        </form>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'IndexHeader',
}
</script>

<style lang="scss" scoped>
    header {
        background-color: black;
        height: 10vh;
    }

    nav {
        height: 10vh;

        img {
            height: 100%;
        }
    }


</style>