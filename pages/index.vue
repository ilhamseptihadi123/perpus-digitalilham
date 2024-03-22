<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
            <nuxt-link to="/pengunjung/tambah">
                <div class="card bg-kunjung rounded-5">
                    <div class="card-body">
                        <h2>Pengujung</h2>
                    </div>
                </div>
            </nuxt-link>
            </div>

        <div class="col-lg-6">
            <nuxt-link to="/buku">
                <div class="card bg-buku rounded-5">
                    <div class="card-body">
                        <h2>Cari Buku</h2>
                    </div>
                </div>
            </nuxt-link>
        </div>
    </div>
    </div>
</template>

<style scoped>
.card{
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-kunjung {
    background-image: url("../assets/img/kunjung.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}
.card.bg-buku {
    background: url("../assets/img/bg-home-cari-buku.jpg") no-repeat center center;
    background-size: cover;
}
</style>