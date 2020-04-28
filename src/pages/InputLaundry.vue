<template>
    <q-page padding>
        <q-card flat >
            <q-card-section class="q-gutter-md">
                <div class="text-h5">Input Jadwal</div>
                <q-form
                @submit="onSubmit"
                @reset="onReset"
                class="q-mt-lg"
                >
                    <div class="q-gutter-md">
                        <q-input label="Nama" v-model="nama" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Nama']"></q-input>
                        <q-input label="Berat" v-model="berat" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Berat']"></q-input>
                        <q-input label="Harga" v-model="harga" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Harga']"></q-input>
                        <q-input label="Tanggal Pengambilan" v-model="tanggal_pengambilan" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Tanggal Pengambilan']"></q-input>
                        <q-btn type="submit" label="Input" color="grey" unelevated></q-btn>
                        <q-btn type="reset" label="Reset" color="grey" flat unelevated></q-btn>
                    </div>
                </q-form>
            </q-card-section>
        </q-card>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      nama: null,
      berat: null,
      harga: null,
      tanggal_pengambilan: null
    }
  },
  methods: {
    onReset () {
      this.nama = null
      this.berat = null
      this.harga = null
      this.tanggal_pengambilan = null
    },
    onSubmit () {
      this.$q.notify({
        type: 'positive',
        message: 'Berhasil Laundry'
      })
      this.$router.push({ name: 'dashboard' })
    }
  }
}
</script>
