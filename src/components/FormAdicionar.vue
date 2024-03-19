<template>
    <div class="content">
        <div class="form">
            <form id="storage-form">
                <div class="input-group">
                    <label for="nome">Nome do Produto: </label>
                    <input type="text" id="nome" name="nome" placeholder="Digite o nome do porduto">
                </div>
                <div class="input-group">
                    <label for="tipo">Tipo do Produto: </label>
                    <select name="tipo" id="tipo">
                        <option value="" selected disabled>Selecione o tipo</option>
                        <option value="papel">Papelaria</option>
                        <option value="descartavel">Descartável</option>
                        <option value="caneta">Caneta</option>
                    </select>
                </div>
                <div class="input-group">
                    <label for="quantidade">Quantidade (Unidade): </label>
                    <input type="number">
                </div>
                <div class="input-group">
                    <label for="descricao">Descrição do Produto: </label><br>
                    <textarea name="descricao" id="descricao"           placeholder="Adicione uma descrição para o produto"></textarea>
                </div>
                <div class="input-group">
                    <input type="submit" class="submit-btn" value="Salvar">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FormAdicionar'
}
</script>

<style scoped lang="scss">
.content {
    font-size: 2rem;

    .form {
        display: flex;
        flex-direction: column;
        align-items: center;

        padding: 1rem;
        width: 65rem;
        height: auto;

        background-color: #eee;
        border: .4rem solid #ccc;

        .input-group {
            margin-top: 1rem;
            padding: .5rem;
            width: 45rem;
            height: auto;
            font-size: 2.5rem;

            label{
                display: block;
                padding: .5rem 1rem;
                margin-bottom: .1rem;
            }

            input, select, textarea {
                width: 45rem;
                height: 4rem;
                padding: .5rem 1rem;
                font-size: 2.5rem;
                border-radius: 1.2rem;
            }
            
            textarea{
                margin-top: -2rem;
                height: 15rem;
                font-size: 1.8rem;
            }

            .submit-btn{
                background-color: #ccc;
                font-weight: bold;
                border: .2rem solid #ccc;
                padding: 1rem;
                font-size: 1.8rem;
                margin: 0 auto;
                cursor: pointer;
                transition: .5s;
            }

            .submit-btn:hover{
                background-color: transparent;
                color: darkcyan;
            }
        }
    }
}
</style>