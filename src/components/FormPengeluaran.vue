<template>
    <form action="" class="form-pengeluaran" @submit.prevent="inputCatatan">
        <div>
            <label for="">Pengeluaran</label>
            <input v-model="pengeluaran" type="number" id="pengeluaran" placeholder="input nominal">
        </div>
        <div>
            <label for="">Keterangan</label>
            <input v-model="keterangan" type="text" id="keterangan" placeholder="input keterangan">
        </div>
        <div>
          <button>Input</button>
        </div>
    </form>
</template>

<script>
export default {
    data(){
        return{
            pengeluaran: null,
            keterangan: null,
        }
    },
    methods:{
        inputCatatan(){
            this.$emit('entri-pengeluaran', {
                nominal : this.pengeluaran,
                keterangan : this.keterangan,
            });
            this.pengeluaran = null;
            this.keterangan = null;
            document.getElementById("pengeluaran").focus(); 
        }
    }
}
</script>

<style scoped>
    .form-pengeluaran{
        display: flex;
        padding: 20px;
        flex-flow: row wrap;
        align-items: center;
        justify-content: center;
    }

    .form-pengeluaran label{
      margin: 1px 10px 5px 0;
    }

    .form-pengeluaran input{
        border: 1px solid #04AA6D;
        vertical-align: middle;
        margin: 5px 10px 5px 0;
        padding: 10px;
        background-color:#fff ;
        border-radius: 2px;
    }
    
    .form-pengeluaran button{
        background-color: #04AA6D;
        border: 1px solid #04AA6D;
        padding: 10px 20px;
        color: #fff;
        border-radius: 2px;
    }

    .form-pengeluaran button:hover{
        background-color: #0dbd7c;
    }

</style>