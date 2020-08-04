<template>
  <div>
    <b-row class="px-3">
      <p class="text-monospace mb-2 text-light">
        Featured
      </p>
    </b-row>
    <b-row class="px-3">
      <b-card-group deck>
        <b-card v-for="(i, index) in 4" :key="index" footer-class="py-1">
          <b-card-text>
            <h5 class="card-title">
              <span class="badge badge-custom">#Topic</span>
            </h5>
            <h4 class="card-title">
              This is actually a title
            </h4>
            <p class="card-text">
              This is a wider card with supporting text below as a natural lead-in to additional content.
              This card has even longer content than the first to show that equal height action.
            </p>
          </b-card-text>
          <template v-slot:footer>
            <small class="text-muted text-right">
              <a href="#" class="stretched-link text-decoration-none">5 minute read</a>
            </small>
          </template>
        </b-card>
      </b-card-group>
    </b-row>
    <b-row class="px-3 py-3">
      <h4 class="my-4">
        Collections
      </h4>
      <b-card-group columns class="mb-3">
        <b-card
          v-for="(i, index) in 6"
          :key="index"
          no-body
          footer-class="py-1"
          align="center"
          class="overflow-hidden"
        >
          <b-row no-gutters>
            <b-col md="4">
              <b-card-img src="https://picsum.photos/400/400/?image=20" alt="Image" class="rounded-0" />
            </b-col>
            <b-col md="8">
              <b-card-body title="#Topic">
                <b-card-text>
                  12 Articles
                </b-card-text>
              </b-card-body>
            </b-col>
          </b-row>
        </b-card>
      </b-card-group>
    </b-row>
    <b-row class="mb-4">
      <b-col sm="6">
        <b-card bg-variant="dark" text-variant="white" title="Card Title" class="mb-3">
          <b-card-text>
            With supporting text below as a natural lead-in to additional content.
          </b-card-text>
          <b-button href="#" variant="primary">
            Go somewhere
          </b-button>
        </b-card>
      </b-col>
      <b-col sm="6">
        <b-card bg-variant="dark" text-variant="white" title="Card Title" class="mb-3">
          <b-card-text>
            With supporting text below as a natural lead-in to additional content.
          </b-card-text>
          <b-button href="#" variant="primary">
            Go somewhere
          </b-button>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
};
</script>

<style>
.badge-custom {
  background: rgba(40, 72, 247, 0.3);
  color: rgba(40, 72, 247, 1);
}
</style>
