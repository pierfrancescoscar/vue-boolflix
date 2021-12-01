<template>
  <header class="p-3">
      <section class="container d-flex align-items-center">
          <div class="col-6 logo-section">
              <img class="ps-logo" src="../assets/ps-logo-white.png" alt="">
          </div>
        <div class="col-6 search-section d-flex justify-content-end">
          <input class="me-3 customInput" 
          type="text"
          placeholder="Search a film here..."
          v-model.trim="userSearch"
          @keyup.enter="$emit('search', userSearch)"
          >

          <button class="btn btn-white">
          Search
          </button>
        </div>

      </section>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            userSearch: '',
        }
    }
}
</script>

<style scoped lang="scss">
header {
    background-color: #000000;
    // background-image: linear-gradient(147deg, #000000 0%, #434343 74%);
}
    .ps-logo {
       width: 200px;
    }
    .customInput {
        border: solid 2px white;
        background: transparent;
        color: white;
        padding-left: 12px;
    }

    .customInput::placeholder {
        font-size: 12px;
        background: transparent;
        color: white;
        text-transform: uppercase;
        padding-left: 12px;
    }

    .btn {
    cursor: pointer;
    border-radius: 0px;
    text-decoration: none;
    padding: 12px 18px;
    font-size: 12px;
    line-height: 19px;
    text-transform: uppercase;
    }
    .btn-white {
    border:solid 2px #fff;
    background: transparent;
    color: #fff
}

</style>