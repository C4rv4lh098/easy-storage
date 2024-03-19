<template>
    <div id="products-table">
        <Mensagem :msg="msg" v-show="msg" />
        <div>
            <table>
                <thead>
                    <th> Nome </th>
                    <th> Tipo </th>
                    <th> Quantidade Unitária </th>
                    <th> Descrição </th>
                    <th> Ações </th>
                </thead>
                <tbody v-for="produto in produtos" :key="produto.id">
                    <td>{{ produto.nome }}</td>
                    <td>{{ produto.tipo }}</td>
                    <td>{{ produto.quantidade }}</td>
                    <td>{{ produto.descricao }}</td>
                    <td>
                        <button class="remover-btn" @click="deleteProduto(produto.id)">Remover</button>
                    </td>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
import Mensagem from './Mensagem';

export default {
    name: 'Dashboard',
    data() {
        return {
            produtos: null,
            produtos_id: null,
            msg: null
        }
    },
    methods: {
        async getProdutos() {
            const req = await fetch("http://localhost:3000/produtos")
            const data = await req.json();

            this.produtos = data;
        },

        async deleteProduto(id) {
            const req = await fetch(`http://localhost:3000/produtos/${id}`, {
                method: "DELETE"
            });

            const res = await req.json();

            this.msg = `Produto ${id} removido do estoque!`
            setTimeout(() => this.msg = "", 3000);
            console.log((res));

            this.getProdutos();
        }
    },
    mounted() {
        this.getProdutos();
    },
    components: {
        Mensagem
    }
}
</script>

<style scoped>
table {
    border: .5rem solid #d4d4d4;
    width: 130rem;
    height: auto;
    padding: 1rem;
    font-weight: bold;
}

th {
    width: 30rem;
    font-size: 3.2rem;
    border: .5rem solid #eee;
    border-bottom: .5rem solid #d4d4d4;
}

td {
    text-align: center;
    padding: .8rem;
    width: 30rem;
    font-size: 2rem;
    border: .2rem solid #eee;
    border-bottom: .3rem solid #d4d4d4;
}

button {
    color: #fff;
    font-weight: bold;
    padding: 1rem;
    font-size: 1.6rem;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
    margin-right: 1rem;
    margin-left: 1rem;
    border-radius: 1.2rem;
}

.editar-btn {
    background-color: green;
    border: .2rem solid gree;
}

.editar-btn:hover {
    background-color: transparent;
    color: green;
}

.remover-btn {
    background-color: red;
    border: .2rem solid red;
}

.remover-btn:hover {
    background-color: transparent;
    color: red;
}
</style>