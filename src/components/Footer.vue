<template>
  <footer class="p-5">
    <section class="container-fluid">
      <section class="container">
            <div class="row">
          <div class="col-4">
              <nav>
                <ul class="list-unstyled">
                  <li class="mb-4">
                    <a class="text-uppercase h6" href="#"><strong>Where all began</strong></a>
                  </li>
                  <li>
                    <a href="#">My idea</a>
                  </li>
                  <li>
                    <a href="#">Concept</a>
                  </li>
                  <li>
                    <a href="#">Why so minimal?</a>
                  </li>
                  <li>
                    <a href="#">Why it works?</a>
                  </li>
                </ul>
              </nav>
            </div>
          <div class="col-4">
              <nav>
                <ul class="list-unstyled">
                  <li class="mb-4">
                    <a class="text-uppercase h6" href="#"><strong>Thanks to</strong></a>
                  </li>
                  <li>
                    <a href="#">My school friends</a>
                  </li>
                  <li>
                    <a href="#">My teachers</a>
                  </li>
                  <li>
                    <a href="#">My fears</a>
                  </li>
                  <li>
                    <a href="#">My doubts</a>
                  </li>
                </ul>
              </nav>
            </div>
          <div class="col-4">
              <nav>
                <ul class="list-unstyled">
                  <li class="mb-4">
                    <a class="text-uppercase h6" href="#"><strong>A new chapter</strong></a>
                  </li>
                  <li>
                    <a href="#">My life with Frontend</a>
                  </li>
                  <li>
                    <a href="#">Time to change</a>
                  </li>
                  <li>
                    <a href="#">Time flies but you're the pilot</a>
                  </li>
                  <li>
                    <a href="#">See you again</a>
                  </li>
                </ul>
              </nav>
            </div>
          </div>
          <div class="row mt-5">
            <div class="col-12">
              <span class="fw-light text-white">Made with love - by Pierfrancesco Scarinci #45</span>
            </div>
          </div>
      </section>
    </section>
  </footer>
</template>

<script>
export default {
    name: 'Footer',
}
</script>

<style scoped lang="scss">
footer {
    background-color: black;
    background-image:linear-gradient(rgba(0, 0, 0, 1), rgba(0, 0, 0, 0.7)), url('https://images.pexels.com/photos/109669/pexels-photo-109669.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260');
    background-position: center;
    background-size: cover;
}

  a {
    color: white;
    text-decoration: none;
    font-size: 14px;
  &:hover {
    color: goldenrod;
  }
  }

span {
  font-size: 12px;
}


</style>