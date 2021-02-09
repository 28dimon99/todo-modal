<template>
    <div id="app">
        <h1>ТАБЛИЦА</h1>
        <table>
            <thead>
            <tr>
                <th>Фамилия</th>
                <th>Имя</th>
                <th>Отчетво</th>
                <th>Дата рождения</th>
                <th>Должность</th>
            </tr>
            </thead>

            <tbody>
            <tr>

                <td><input :value='surname' @input="inputChangeSurname" placeholder="Введите фамилию"  type="text"></td>
                <td><input :value='name' @input="inputChangeName" placeholder="Введите имя" type="text"></td>
                <td><input :value='patro' @input="inputChangePatro" placeholder="Введите отчество" type="text"></td>
                <td><input :value='date' @input="inputChangeDate" placeholder="Введите дату рождения" type="text"></td>
                <td><input :value='position' @input="inputChangePosition" placeholder="Введите должность" type="text"></td>
                <td>
                    <a class="waves-effect waves-light btn" @click="showModal">Редактировать</a>
                </td>


            </tr>

            <tr>
                <td>
                    <a class="waves-effect waves-light btn-small red"
                       @click='removeSurname'>Удалить</a>
                </td>
                <td>
                    <a class="waves-effect waves-light btn-small red"
                       @click='removeName'>Удалить</a>
                </td>
                <td>
                    <a class="waves-effect waves-light btn-small red"
                       @click='removePatro'>Удалить</a>

                </td>
                <td>
                    <a class="waves-effect waves-light btn-small red"
                       @click='removeDate'>Удалить</a>
                </td>
                <td>
                    <a class="waves-effect waves-light btn-small red"
                       @click='removePosition'>Удалить</a>
                </td>
            </tr>

            </tbody>
        </table>

        <Modal
                v-if="isModal"
                @closeModal="closeModal"
        >
            <form>
                <div class="form-items">
                    Фамилия<input v-model="surname" placeholder="Введите фамилию" type="text"/>
                    <i class="material-icons" @click="removeSurname">delete</i>
                </div>
                <div class="form-items">
                    Имя<input v-model="name" placeholder="Введите имя" type="text"/><i
                        class="material-icons" @click="removeName">delete</i>
                </div>
                <div class="form-items">
                    Отчество<input v-model="patro" placeholder="Введите отчество" type="text"/><i
                        class="material-icons" @click="removePatro">delete</i>
                </div>
                <div class="form-items">
                    Дата рождения<input v-model="date" placeholder="Введите дату рождения"  type="text"/><i
                        class="material-icons" @click="removeDate">delete</i>
                </div>
                <div class="form-items">
                    Должность<input v-model="position" placeholder="Введите должность"  type="text"/><i
                        class="material-icons" @click="removePosition">delete</i>
                </div>

            </form>
        </Modal>
    </div>
</template>

<script>
    import Modal from "./components/Modal";


    export default {
        name: 'App',
        data() {
            return {
                isModal: false,

                    surname: '',
                    name: '',
                    patro: '',
                    date: '',
                    position: '',
            }
        },
        methods: {
            showModal() {
                this.isModal = true
            },
            closeModal() {
                this.isModal = false
            },

            removeSurname() {
                this.surname = ''
            },
            removeName(){
                this.name = ''
            },
            removePatro(){
                this.patro = ''
            },
            removeDate(){
                this.date = ''
            },
            removePosition(){
                this.position = ''
            },

            inputChangeSurname(event) {
                this.surname = event.target.value
            },
            inputChangeName(event){
                this.name = event.target.value
            },
            inputChangePatro(event){
                this.patro = event.target.value
            },
            inputChangeDate(event){
                this.date = event.target.value
            },
            inputChangePosition(event){
                this.position = event.target.value
            },
        },

            components: {
                Modal
            }

    }
</script>

<style lang="scss">
    @import "~materialize-css/dist/css/materialize.min.css";

    #app {
        display: grid;
        margin-top: 100px;
        justify-content: center;
        border: 1px solid black;
        text-align: center;
        background-color:#00838f ;
    }
    .form-items{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;

    }


</style>
