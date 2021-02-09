<template>
    <div class="modal">
        <div class="content">
            <h3>Редактировать поля</h3>
            <span class="close-modal">
            <i class="material-icons"
               @click="closeModal">close
            </i>
        </span>
           <slot>

           </slot>

            <div class="modal-footer">
                <a class="waves-effect waves-light btn-small close_modal red"
                   @click="closeModal">Закрыть</a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Modal",
        props:{},
        data: () => ({

        }),
        methods:{
            closeModal(){
                this.$emit("closeModal")
            },

        },


    }
</script>

<style scoped>
    .modal {
        display: grid;
        position: fixed;
        z-index: 999999999;
        top:50px;
        border:  3px solid black;
        border-radius: 10px;
        width: 800px;
        height: 500px;
        background-color:#eceff1;
    }
    .close-modal{
        position: absolute;
        top:0;
        right: 0;
        background-color: red;
        color: white;
    }


</style>