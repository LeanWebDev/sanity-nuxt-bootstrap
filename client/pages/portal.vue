<template>
  <div>
    <b-row>
      <b-col sm="2">
        <div class="sticky-top pt-sm-5 mb-3">
          <b-list-group v-b-scrollspy:listgroup-ex>
            <b-list-group-item href="#account">
              Account
            </b-list-group-item>
            <b-list-group-item href="#support">
              Support
            </b-list-group-item>
            <b-list-group-item href="#solutions">
              Solutions
            </b-list-group-item>
          </b-list-group>
        </div>
      </b-col>
      <b-col sm="8">
        <b-row id="account" class="">
          <b-col>
            <h5>Account</h5>
            <p class="text-muted">
              Manage your details here.
            </p>
            <b-card class="shadow-sm" header="Profile">
              <b-form @submit="onSubmit" @reset="onReset">
                <b-form-group
                  id="input-group-1"
                  label="Email address"
                  label-for="input-1"
                  description="We'll never share your email with anyone else."
                >
                  <b-form-input
                    id="input-1"
                    v-model="form.email"
                    type="email"
                    required
                    placeholder="Enter email"
                  />
                </b-form-group>

                <b-form-group id="input-group-2" label="Full name" label-for="input-2">
                  <b-form-input
                    id="input-2"
                    v-model="form.name"
                    required
                    placeholder="Enter name"
                  />
                </b-form-group>

                <b-form-group id="input-group-3" label="Industry" label-for="input-3">
                  <b-form-select
                    id="input-3"
                    v-model="form.industry"
                    :options="industrys"
                    required
                  />
                </b-form-group>
                <b-button v-if="editable" variant="secondary" class="float-right" @click="editable == true">
                  Edit
                </b-button>
                <b-button v-if="editable" type="submit" variant="success" class="float-right" @click="!editable">
                  Update
                </b-button>
              </b-form>
            </b-card>
          </b-col>
        </b-row>
        <hr class="my-4">
        <b-row id="support">
          <b-col>
            <h5>Support</h5>
            <p class="text-muted">
              Manage your cases here.
            </p>
            <b-card class="shadow-sm " header="Cases" no-body>
              <b-table
                sticky-header
                responsive
                hover
                :items="items"
                class="mb-0"
                stacked="md"
                :fields="fields"
                :per-page="perPage"
                :filter="filter"
                :filter-included-fields="filterOn"
                :sort-by.sync="sortBy"
                :sort-desc.sync="sortDesc"
                :sort-direction="sortDirection"
                @filtered="onFiltered"
              >
                <template v-slot:cell(name)="row">
                  {{ row.value.first }} {{ row.value.last }}
                </template>

                <template v-slot:cell(actions)="row">
                  <b-button size="sm" class="mr-1" @click="info(row.item, row.index, $event.target)">
                    Show Details
                  </b-button>
                  <!-- <b-button size="sm" @click="row.toggleDetails">
                    {{ row.detailsShowing ? 'Hide' : 'Show' }} Details
                  </b-button> -->
                </template>

                <template v-slot:row-details="row">
                  <b-card>
                    <ul>
                      <li v-for="(value, key) in row.item" :key="key">
                        {{ key }}: {{ value }}
                      </li>
                    </ul>
                  </b-card>
                </template>
              </b-table>
            </b-card>
          </b-col>
        </b-row>
        <hr class="my-4">
        <b-row id="solutions">
          <b-col>
            <h5>Solutions</h5>
            <p class="text-muted">
              Manage your products and services here.
            </p>
            <b-card class="shadow-sm " no-body>
              <b-tabs card>
                <b-tab title="Connectivity" active>
                  <b-card-text>
                    <b-list-group>
                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Connectivity Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>

                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Connectivity Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>
                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Connectivity Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>
                    </b-list-group>
                  </b-card-text>
                </b-tab>
                <b-tab title="Security">
                  <b-card-text>
                    <b-list-group>
                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Security Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>

                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Security Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>
                      <b-list-group-item disabled class="flex-column align-items-start">
                        <div class="d-flex w-100 justify-content-between">
                          <h5 class="mb-1">
                            Security Product
                          </h5>
                          <small class="text-muted"><b-badge variant="primary">July 2020</b-badge></small>
                        </div>

                        <p class="mb-1">
                          Product details
                        </p>
                        <div>
                          <b-badge pill variant="dark">
                            Juniper
                          </b-badge>
                          <b-badge pill variant="dark">
                            Managed
                          </b-badge>
                        </div>
                      </b-list-group-item>
                    </b-list-group>
                  </b-card-text>
                </b-tab>
              </b-tabs>
            </b-card>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
    <b-modal :id="infoModal.id" :title="infoModal.title" ok-only @hide="resetInfoModal">
      <p>{{ infoModal.content }}</p>
    </b-modal>
  </div>
</template>
<script>
export default {
  layout: 'account',
  data () {
    return {
      form: {
        editable: false,
        email: '',
        name: '',
        industry: null,
        checked: []
      },
      industrys: [{ text: 'Select One', value: null }, 'Software', 'Hospitality', 'Entertainment', 'Retail'],
      items: [
        { isActive: true, age: 40, name: { first: 'OPF2324', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: false, age: 21, name: { first: 'OPFA3431', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        {
          isActive: false,
          age: 9,
          name: { first: 'OP4589991', last: '' },
          desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.',
          _rowVariant: 'success'
        },
        { isActive: false, age: 89, name: { first: 'OPAR3423', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: true, age: 38, name: { first: 'OPYY6744', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: false, age: 27, name: { first: 'OP212445', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: true, age: 40, name: { first: 'OPERT4754', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        {
          isActive: true,
          age: 87,
          name: { first: 'OP46352F3', last: '' },
          desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.',
          _cellVariants: { age: 'danger', isActive: '' }
        },
        { isActive: false, age: 26, name: { first: 'OP41214', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: false, age: 22, name: { first: 'OP53463', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: true, age: 38, name: { first: 'OP67561', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' },
        { isActive: false, age: 29, name: { first: 'OP63246', last: '' }, desc: 'This is some sample text just to fill up some space and illustrate what this modal might look like with some content.' }
      ],
      fields: [
        { key: 'name', label: 'Case ID', sortable: true },
        { key: 'age', label: 'Case age (Days)', sortable: true, class: 'text-center', sortDirection: 'asc' },
        {
          key: 'isActive',
          label: 'Status',
          formatter: (value, key, item) => {
            return value ? 'Resolved' : 'Pending'
          },
          sortable: true,
          sortByFormatted: true,
          filterByFormatted: true
        },
        { key: 'actions', label: 'Actions' }
      ],
      totalRows: 1,
      currentPage: 1,
      perPage: 5,
      pageOptions: [5, 10, 15],
      sortBy: '',
      sortDesc: false,
      sortDirection: 'asc',
      filter: null,
      filterOn: [],
      infoModal: {
        id: 'info-modal',
        title: '',
        content: ''
      }
    }
  },
  computed: {
    sortOptions () {
      // Create an options list from our fields
      return this.fields
        .filter(f => f.sortable)
        .map((f) => {
          return { text: f.label, value: f.key }
        })
    }
  },
  mounted () {
    // Set the initial number of items
    this.totalRows = this.items.length
  },
  methods: {
    info (item, index, button) {
    //   this.infoModal.title = `Row index: ${index}`
      this.infoModal.title = item.name.first
      //   this.infoModal.content = JSON.stringify(item, null, 2)
      this.infoModal.content = item.desc
      this.$root.$emit('bv::show::modal', this.infoModal.id, button)
    },
    resetInfoModal () {
      this.infoModal.title = ''
      this.infoModal.content = ''
    },
    onFiltered (filteredItems) {
      // Trigger pagination to update the number of buttons/pages due to filtering
      this.totalRows = filteredItems.length
      this.currentPage = 1
    },
    onSubmit (evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset (evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.industry = null
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }
}
</script>
<style lang="scss">

</style>
