<template>
<div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h2 class="text-center my-4">ISI KUNJUNGAN</h2>
        <form>
          <div class="mb-3">
            <input type="text" class="form-control form-control-lg rounded-5" placeholder="NAMA" />
            <select v-model ="form.tingkat"></select>
          </div>
          <div class="mb-3">
            <select class="form-control from-control-lg form-select rounded-5">
              <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
            </select>
          </div>
          <div class="mb-3">
            <div class="rwo">
              <div class="col-md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">TINGKAT</option>
                  <option value="X">X</option>
                  <option value="XI">XI</option>
                  <option value="XII">XII</option>
                </select>
              </div>
              <div class="col-md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">JURUSAN</option>
                  <option value="PPLG">PPLG</option>
                  <option value="TJKT">TJKT</option>
                  <option value="TSM">TSM</option>
                  <option value="DKV">DKV</option>
                  <option value="TOI">TOI</option>
                </select>
              </div>
              <div class="col-md-4">
                <select class="form-control form-control-lg form-select rounded-5 mb-2">
                  <option value="">KELAS</option>
                  <option value="1">1</option>
                  <option value="2">2</option>
                  <option value="3">3</option>
                  <option value="4">4</option>
                </select>
              </div>
            </div>
          </div>
          <div class="mb-3">
            <select class="form-control form-control-lg form-select rounded-5">
              <option value="">KEPERLUAN</option>
              <option value="baca">Baca Buku</option>
              <option value="pinjam">Pinjam Buku</option>
              <option value="Kembalikan">Kembalikan Buku</option>
            </select>
          </div>
          <NuxtLink to="/pengunjung">
            <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">kirim</button>
          </NuxtLink>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const members = ref([])
const objectives = ref([])

const form = ref({
  nama:"",
  keanggotaan:"",
  tingkat:"",
  jurusan:"",
  kelas:"",
  keperulan:"",
})

const kirimdata = async () => {
  const { error } = await supabase.form('pengunjung').insert([form.value])
  if(!error) navigator('/pengunjung')
}

const getkeanggotaan = async () => {
  const { data,error } = await supabase.form('keanggotaan').select('*')
}

onMounted(() => {
  getkeanggotaan()
  getkeperluan()
})
</script>

<form @submit.prevent="kirimdata">
</form>






