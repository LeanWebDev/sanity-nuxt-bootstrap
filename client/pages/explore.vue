<template>
  <div>
    <b-row>
      <b-col sm="2">
        <b-tabs pills vertical fill nav-wrapper-class="w-100">
          <b-tab title="Tab 1" active />
          <b-tab title="Tab 2" />
          <b-tab title="Tab 3" />
        </b-tabs>
      </b-col>
      <b-col sm="10">
        <b-card>This is a card</b-card>
      </b-col>
    </b-row>
  </div>
</template>
<script>
export default {
  layout: 'content'
}
</script>
<style lang="scss">

</style>
