<template>
  <div>
    <b-row>
      <b-col sm="2">
        <b-tabs pills vertical fill nav-wrapper-class="w-100">
          <b-tab active>
            <template v-slot:title>
              <b-icon icon="wifi" class="mr-2" />WiFi (12)
            </template>
          </b-tab>
          <b-tab>
            <template v-slot:title>
              <b-icon icon="cloud" class="mr-2" />Cloud (17)
            </template>
          </b-tab>
          <b-tab>
            <template v-slot:title>
              <b-icon icon="cpu" class="mr-2" />Hardware (8)
            </template>
          </b-tab>
          <b-tab>
            <template v-slot:title>
              <b-icon icon="credit-card" class="mr-2" />Payments (6)
            </template>
          </b-tab>
          <b-tab>
            <template v-slot:title>
              <b-icon icon="cursor" class="mr-2" />MacOS (22)
            </template>
          </b-tab>
          <b-tab>
            <template v-slot:title>
              <b-icon icon="diagram3" class="mr-2" />Networks (32)
            </template>
          </b-tab>
        </b-tabs>
      </b-col>
      <b-col sm="10">
        <b-row class="px-3">
          <b-col>
            <h1>Articles</h1>
          </b-col>
        </b-row>
        <b-row no-gutters class="px-3">
          <div v-for="(i, index) in 10" :key="index" class="col-sm-4">
            <b-card class="mx-2 my-2 shadow-sm" footer-class="py-1">
              <b-card-text>
                <h5 class="card-title">
                  <span class="badge badge-custom">#Topic</span>
                </h5>
                <h4 class="card-title">
                  This is actually a title
                </h4>
                <p class="card-text">
                  This is a wider card with supporting text below as a natural lead-in to additional content.
                </p>
              </b-card-text>
              <template v-slot:footer>
                <small class="text-muted text-right">
                  <a href="/article" class="stretched-link text-decoration-none">5 minute read</a>
                </small>
              </template>
            </b-card>
          </div>
        </b-row>
        <b-row>
          <b-col>
            <div class="mt-3">
              <b-pagination v-model="currentPage" :total-rows="rows" align="center" />
            </div>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  layout: 'content',
  data () {
    return {
      rows: 100,
      currentPage: 3,
      articles: [
        { name: 'WiFi', icon: 'broadcast', count: 12 },
        { name: 'Cloud', icon: 'cloud', count: 17 },
        { name: 'Hardware', icon: 'cpu', count: 8 },
        { name: 'Payments', icon: 'credit-card', count: 6 },
        { name: 'MacOS', icon: 'cursor', count: 22 },
        { name: 'Networks', icon: 'diagram3', count: 32 }
      ]
    }
  }
}
</script>
<style lang="scss">

</style>
