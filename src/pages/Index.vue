<template>
  <q-page padding>
     <q-table
      title="List Laundry DOJO"
      :data="data"
      :columns="columns"
      row-key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="nama" :props="props">
            {{ props.row.nama }}
          </q-td>
          <q-td key="berat" :props="props">
            {{ props.row.berat }}
          </q-td>
          <q-td key="harga" :props="props">
            {{ props.row.harga }}
          </q-td>
          <q-td key="tanggal_pengambilan" :props="props">
            {{ props.row.tanggal_pengambilan }}
          </q-td>
          <q-td key="aksi" :props="props">
            <div class="row">
              <div class="col">
                <q-btn label="Sudah Diambil" color="blue" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Edit" color="green" icon="edit" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Hapus" color="negative" icon="delete" unelevated></q-btn>
              </div>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'nama',
          required: true,
          label: 'Nama',
          align: 'left',
          field: 'nama',
          sortable: true
        },
        { name: 'berat', align: 'center', label: 'Berat', field: 'berat', sortable: true },
        { name: 'harga', label: 'Harga', align: 'center', field: 'harga', sortable: true },
        { name: 'tanggal_pengambilan', label: 'Tanggal Pengambilan', align: 'center', field: 'tanggal_pengambilan', sortable: true },
        { name: 'aksi', label: 'Aksi', field: 'aksi', align: 'center' }
      ],

      data: [
        {
          nama: 'Destri',
          berat: '3 kg',
          harga: '45.000',
          tanggal_pengambilan: '10 Mei 2020'
        },
        {
          nama: 'Mara',
          berat: '20 kg',
          harga: '300.000',
          tanggal_pengambilan: '1 Juni 2020'
        },
        {
          nama: 'Yolla',
          berat: '1 kg',
          harga: '15.000',
          tanggal_pengambilan: '1 Mei 2020'
        }
      ]
    }
  }
}
</script>
