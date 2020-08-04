<template>
  <div>
    <b-container fluid="true" class="px-0">
      <b-jumbotron
        bg-variant="info"
        text-variant="white"
        border-variant="info"
        fluid="true"
        container-fluid="true"
        class="my-0 py-1 text-center"
      >
        <a href="#" class="m-0 text-white">
          It uses utility classes for typography and spacing to space content
          out within the larger container.
          <b-badge variant="primary" class="ml-2">New</b-badge>
        </a>
      </b-jumbotron>
      <b-navbar class="border-bottom">
        <b-container>
          <b-navbar-brand href="#" class="text-primary">
            Optimity
          </b-navbar-brand>
          <b-navbar-nav class="ml-auto">
            <b-nav-item>
              <b-button
                size="sm"
                class="my-2 my-sm-0"
                variant="primary"
              >
                Customer Portal
              </b-button>
            </b-nav-item>
          </b-navbar-nav>
        </b-container>
      </b-navbar>
    </b-container>
    <b-container fluid="sm" class="pt-3">
      <Nuxt />
    </b-container>
  </div>
</template>

<style lang="scss">
</style>
