<template>
  <div>
    <b-row>
      <b-col sm="10" offset="1">
        <b-card
          overlay
          img-src="https://picsum.photos/1000/200/?image=3"
          img-alt="Card Image"
          align="center"
        />
      </b-col>
      <b-col sm="10" offset="1" class="pt-4">
        <h2 class="blog-post-title">
          Sample post
        </h2>
        <p class="blog-post-meta">
          January 1, 2021 by <a href="#">Mark</a>
        </p>

        <p>This blog post shows a few different types of content that’s supported and styled with Bootstrap. Basic typography, images, and code are all supported.</p>
        <hr>
        <p>Cum sociis natoque penatibus et magnis <a href="#">dis parturient montes</a>, nascetur ridiculus mus. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Sed posuere consectetur est at lobortis. Cras mattis consectetur purus sit amet fermentum.</p>
        <blockquote>
          <p>Curabitur blandit tempus porttitor. <strong>Nullam quis risus eget urna mollis</strong> ornare vel eu leo. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
        </blockquote>
        <p>Etiam porta <em>sem malesuada magna</em> mollis euismod. Cras mattis consectetur purus sit amet fermentum. Aenean lacinia bibendum nulla sed consectetur.</p>
        <h2>Heading</h2>
        <p>Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <h3>Sub-heading</h3>
        <p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
        <pre><code>Example code block</code></pre>
        <p>Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa.</p>
        <h3>Sub-heading</h3>
        <p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        <ul>
          <li>Praesent commodo cursus magna, vel scelerisque nisl consectetur et.</li>
          <li>Donec id elit non mi porta gravida at eget metus.</li>
          <li>Nulla vitae elit libero, a pharetra augue.</li>
        </ul>
        <p>Donec ullamcorper nulla non metus auctor fringilla. Nulla vitae elit libero, a pharetra augue.</p>
        <ol>
          <li>Vestibulum id ligula porta felis euismod semper.</li>
          <li>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</li>
          <li>Maecenas sed diam eget risus varius blandit sit amet non magna.</li>
        </ol>
        <p>Cras mattis consectetur purus sit amet fermentum. Sed posuere consectetur est at lobortis.</p>
      </b-col>
    </b-row>
    <b-row class="px-3">
      <b-col sm="10" offset="1">
        <p class="text-monospace mb-2 text-dark">
          Related articles
        </p>
        <b-card-group deck>
          <b-card v-for="(i, index) in 3" :key="index" class="shadow-sm" footer-class="py-1">
            <b-card-text>
              <h5 class="card-title">
                <span class="badge badge-custom">#Topic</span>
              </h5>
              <h4 class="card-title">
                This is actually a title
              </h4>
              <p class="card-text">
                This is a wider card with supporting
              </p>
            </b-card-text>
            <template v-slot:footer>
              <small class="text-muted text-right">
                <a href="#" class="stretched-link text-decoration-none">5 minute read</a>
              </small>
            </template>
          </b-card>
        </b-card-group>
      </b-col>
    </b-row>
    <b-row class="mb-4 mt-5">
      <b-col sm="5" offset="1">
        <b-card bg-variant="dark" text-variant="white" title="Promotion" class="mb-3">
          <b-card-text>
            With supporting text below as a natural lead-in to additional content.
          </b-card-text>
          <b-button href="#" variant="primary">
            Go somewhere
          </b-button>
        </b-card>
      </b-col>
      <b-col sm="5">
        <b-card bg-variant="dark" text-variant="white" title="Promotion" class="mb-3">
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
  layout: 'content',
  data () {
    return {
    }
  }
}
</script>
<style lang="scss">
.badge-custom {
  background: rgba(40, 72, 247, 0.3);
  color: rgba(40, 72, 247, 1);
}
</style>
