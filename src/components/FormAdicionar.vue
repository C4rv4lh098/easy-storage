<template>
    <div class="content">
        <Mensagem :msg="msg" v-show="msg" />
        <div class="form">
            <form id="storage-form" @submit="createProduto">
                <div class="input-group">
                    <label for="nome">Nome do Produto: </label>
                    <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite o nome do porduto">
                </div>
                <div class="input-group">
                    <label for="tipo">Tipo do Produto: </label>
                    <select name="tipo" id="tipo" v-model="tipo">
                        <option value="" disabled>Selecione o tipo</option>
                        <option v-for="tipo in tipos" :key="tipo.id" :value="tipo.tipo">
                            {{ tipo.tipo }}
                        </option>
                    </select>
                </div>
                <div class="input-group">
                    <label for="quantidade">Quantidade (Unidade): </label>
                    <input type="number" v-model="quantidade">
                </div>
                <div class="input-group">
                    <label for="descricao">Descrição do Produto: </label><br>
                    <textarea name="descricao" id="descricao" v-model="descricao"
                        placeholder="Adicione uma descrição para o produto"></textarea>
                </div>
                <div class="input-group">
                    <input type="submit" class="submit-btn" value="Salvar">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import Mensagem from './Mensagem'

export default {
    name: 'FormAdicionar',
    data() {
        return {
            nome: null,
            tipos: null,
            quantidade: null,
            descricao: null,
            tipo: null,
            msg: null
        }
    },
    methods: {
        async getTipos() {
            const req = await fetch("http://localhost:3000/tipos")
            const data = await req.json();

            this.tipos = data.tipos;
            console.log(this.tipos)
        },

        async createProduto(e) {
            e.preventDefault();

            const data = {
                nome: this.nome,
                tipo: this.tipo,
                quantidade: this.quantidade,
                descricao: this.descricao
            }

            const dataJson = JSON.stringify(data);
            const req = await fetch("http://localhost:3000/produtos", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            const res = await req.json();
            this.msg = `Produto Nº ${res.id} cadastrado!`
            setTimeout(() => this.msg = "", 3000);

            this.nome = "";
            this.tipo = "";
            this.quantidade = "";
            this.descricao = "";
        }
    },
    mounted() {
        this.getTipos();
    },
    components: {
        Mensagem
    }
}
</script>

<style scoped>
.content {
    font-size: 2rem;
}

.form {
    display: flex;
    flex-direction: column;
    align-items: center;

    padding: 1rem;
    width: 65rem;
    height: auto;

    background-color: #eee;
    border: .4rem solid #ccc;
}

.input-group {
    margin-top: 1rem;
    padding: .5rem;
    width: 45rem;
    height: auto;
    font-size: 2.5rem;
}

label {
    display: block;
    padding: .5rem 1rem;
    margin-bottom: .1rem;
}

input,
select,
textarea {
    width: 45rem;
    height: 4rem;
    padding: .5rem 1rem;
    font-size: 2.5rem;
    border-radius: 1.2rem;
}

textarea {
    margin-top: -2rem;
    height: 15rem;
    font-size: 1.8rem;
}

.submit-btn {
    background-color: #ccc;
    font-weight: bold;
    border: .2rem solid #ccc;
    padding: 1rem;
    font-size: 1.8rem;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
}

.submit-btn:hover {
    background-color: transparent;
    color: darkcyan;
}
</style>