<template>
    <form @submit.prevent="submitData">
        <div>
            <label>Name</label>
            <input type="name" v-model="enteredName"/>
        </div>
        <div>
            <label>Number</label>
            <input type="tel" v-model="enteredNumber"/>
        </div>
        <div>
            <label>Email</label>
            <input type="email" v-model="enteredEmail"/>
        </div>
        <div>
            <button>Enter</button>
        </div>
    </form>
</template>




<script>
    export default{
        emits:['add-contact'],
        data(){
            return{
                enteredName: '',
                enteredNumber: '',
                enteredEmail: ''
            }
        },
        methods:{
            submitData(){
                this.$emit('add-contact', 
                this.enteredName, 
                this.enteredNumber, 
                this.enteredEmail
                )
            }
        }
    }
</script>