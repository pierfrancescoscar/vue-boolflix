<template>

  <div class="card-box">
    <div class="content-box w-100 h-100">
          
        <img class="w-100 h-100" v-if="image !== null" :src="`https://image.tmdb.org/t/p/w185/${image}`" alt="">

         <img v-else class="not-found" src="https://www.publicdomainpictures.net/pictures/280000/velka/not-found-image-15383864787lu.jpg" alt="">


        <ul class="list-unstyled my-list p-2">
            <li><strong>Titolo:</strong> {{ title }} {{name}} </li>

            <li><strong>Titolo Originale:</strong> {{ originalTitle }} {{originalName}}</li>

            <li v-if="languages.includes(lang)">
                <img class="flag" :src="require(`@/assets/${lang}.png`)">
            </li>

            <li v-else> <strong>Lingua:</strong> {{ lang }} </li>
            <li><strong>Voto:</strong> {{ vote }}</li>
            <li>
                <i v-for="(vote, index) in Math.ceil((vote / 2))" :key="`star-${index}`" class="goldenstar fas fa-star"></i>

                <i v-for="(vote, index) in 5 - (Math.ceil((vote / 2)))" :key="`empty-${index}`" class="far fa-star"></i>
            </li>
            <li>
                <strong>Overview:</strong> {{description}}
            </li>
        </ul>

    </div>


      
  </div>

</template>

<script>
export default {
    name: 'Card',
    props: {
        title: String,
        originalTitle: String,
        lang: String,
        vote: Number,
        description: String,

        name: String,
        originalName: String,
        image: String,
    },
    data() {
        return {
            
            languages: ['en', 'it'],
        
        }
    }

}
</script>

<style scoped lang="scss">

.content-box {
    position: relative;
}

    .my-list {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        background: rgba($color: #000000, $alpha: 0.8);
        color: white;
        font-size: 12px;
        opacity: 0;
        &:hover {
            opacity: 1;
            
        }
    }

.flag {
    width: 30px;
}

.not-found {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
}

.goldenstar {
    color: gold;
}
</style>