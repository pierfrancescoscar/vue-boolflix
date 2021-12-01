<template>

    <!-- Hero -->
    <section class="container-fluid px-0">
        <section class="container-fluid jumbotron">
            <div class="container">
                <h1 class="text-uppercase pt-5">Welcome to <br>PS Theater</h1>
                <p class="fw-light">You can find anything here.</p>
                <button class="btn-white text-uppercase mb-5">
                    See more
                </button>
            </div>
        </section>
        <!-- Now Sharing -->
        <section class="container-fluid px-0 p-3 sharing">
            <section class="container">
                <h2 class="share-title pt-5"><strong>Now</strong> Sharing</h2>
                <p class="fw-light">Search a film and enjoy.</p>
            </section>
        </section>
        <!-- Films -->
        <div class="media-container p-5 d-flex flex-wrap w-100">
            <div class="films-box w-100 d-flex flex-wrap">

                <Card v-for="(element, index) in films" :key="`film-${index}`" class="singlecard  mb-3 px-2"
                    :image="element.poster_path"
                    :title="element.title"
                    :originalTitle="element.original_title"
                    :lang="element.original_language"
                    :vote="element.vote_average" 
                    :description="element.overview"
                    />

            </div>

            <div class="series-box d-flex flex-wrap w-100">

                <Card v-for="(element, index) in series" :key="`series-${index}`" class="singlecard mb-3 px-2"
                    :name="element.name"
                    :originalName="element.original_name"
                    :lang="element.original_language"
                    :vote="element.vote_average" 
                    :image="element.poster_path"
                    :description="element.overview"
                    />

            </div>
        </div>

    </section>
  
</template>

<script>
import Card from '@/components/Card.vue';

export default {
    name: 'Main',
    components: {
        Card,
    },
    props: {
        films: Array,
        series: Array,
    }

}
</script>

<style scoped lang="scss">

.jumbotron {
    background-image: url('../assets/ps-jumbotron.png');
    background-size: cover;
}
    h1 {
        color: white;
        font-size: 80px;
        font-weight: 900;
        letter-spacing: 4px;
    }

    p {
        color: white;
    }

    .btn-white {
        border:solid 2px #fff;
        background: transparent;
        color: #fff;
        padding: 12px 18px;
    }

.singlecard {
    width: calc(100% / 5);
    min-height: 250px;
    cursor: pointer;
    overflow: hidden;
    
    
}

.media-container, .sharing {
   background-color: #000000;
    // background-image: linear-gradient(147deg, #000000 0%, #434343 74%);
}
    .share-title {
        color: white;
    }

</style>