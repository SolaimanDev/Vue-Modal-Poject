<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal">
            <!-- <h2>{{header}}</h2> -->
            <slot></slot>
            <div class="actions">
 <slot name="links"></slot>
            </div>
         
        </div>
    </div>
</template>
<script>
export default {
    name: "ModalComponent",
    props: ['header','text'],

    data(){
        return{

        }
    },
    methods:{
        closeModal()
        {
            this.$emit('close');
        }
    }

}
</script>

<style scoped>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px;
    background: white;
    border-radius: 10px;

}
.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}
.modal h2{
    color: darkcyan;
    border: none;
    padding: 0;
}
.modal p{
    font-style: normal;
}
.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
    color: #333;
}
.modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
</style>
