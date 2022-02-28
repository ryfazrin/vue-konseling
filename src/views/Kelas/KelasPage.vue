<template>
  <div>
    <CCard accent-color="primary">
      <CCardHeader>
        Kelas

        <div class="card-header-actions">
          <CButton color="primary" @click="showModal = true">Tambah Kelas</CButton>
          <CModal
            title="Add Kelas"
            :show.sync="showModal"
          >
            <CRow>
              <CCol sm="12">
                <CInput
                  label="Kelas"
                  placeholder="Masukkan Kelas"
                />
              </CCol>
              <CCol sm="12">
                <CInput
                  label="Tahun"
                  placeholder="Masukkan Tahun"
                />
              </CCol>
            </CRow>
            
            <template #footer>
              <CButton color="secondary" @click="showModal = false">Close</CButton>
              <CButton color="primary">Save</CButton>
            </template>
          </CModal>
        </div>
      </CCardHeader>

      <CCardBody>
        
        <CDataTable
          :items="items"
          :fields="fields"
          column-filter
          table-filter
          items-per-page-select
          :items-per-page="5"
          hover
          sorter
          pagination
        >
          <template #show_details="{item, index}">
            <td class="py-2">
              <CButton
                color="primary"
                variant="outline"
                square
                size="sm"
                @click="toggleDetails(item, index)"
              >
                {{Boolean(item._toggled) ? 'Hide' : 'Show'}}
              </CButton>
            </td>
          </template>
          <template #details="{item}">
            <CCollapse :show="Boolean(item._toggled)" :duration="collapseDuration">
              <CCardBody>
                <CMedia :aside-image-props="{ height: 102 }">
                  <h4>
                    Kelas: {{item.kelas}}
                  </h4>
                  <p class="text-muted">Since: {{item.year}}</p>
                  <CButton size="sm" color="info">
                    Edit
                  </CButton>
                  <CButton size="sm" color="danger" class="ml-1">
                    Delete
                  </CButton>
                </CMedia>
              </CCardBody>
            </CCollapse>
          </template>
        </CDataTable>

      </CCardBody>
    </CCard>
  </div>
</template>

<script>
// import AddEditModal from "./AddEditModal";

// data items
const items = [
    {
        no: 1,
        kelas: '10',
        year: '2021',
    },
    {
        no: 2,
        kelas: '11',
        year: '2021',
    },
    {
        no: 3,
        kelas: '12',
        year: '2021',
    },
]

// fields
const fields = [
  { key: 'no', _style:'width:1%' },
  { key: 'kelas' },
  { key: 'year' },
  { 
    key: 'show_details', 
    label: '', 
    _style: 'width:1%', 
    sorter: false, 
    filter: false,
    showModal: false
  }
]

export default {
  name: 'KelasPage',
  data () {
    return {
      items: items.map((item, id) => { return {...item, id}}),
      fields,
      details: [],
      collapseDuration: 0,
      showModal: false
    }
  },
  methods: {
    toggleDetails (item) {
      this.$set(this.items[item.id], '_toggled', !item._toggled)
      this.collapseDuration = 300
      this.$nextTick(() => { this.collapseDuration = 0})
    },
  }
}
</script>

<style>

</style>