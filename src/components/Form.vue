<template>
    <form >
        <div>
            <label for="name">Name</label>
            <input type="text" name="name" v-model="name" id="name">
        </div>
        <div>
            <label for="last_name">Last Name</label>
            <input type="text" name="last_name" v-model="last_name" id="last_name">
        </div>
        
        <button @click="onSubmit" class="btn btn-primary" type="button">Send</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    
    data: ()=>({
        name:null,
        last_name: null
        
    }),

    methods: {
        onSubmit: function (event){
            event.preventDefault();
            console.log('submit')
            let data = {
                name: this.name,
                last_name: this.last_name
            }
            if (data.name && data.last_name){
                this.$emit('data-submited', data);
                this.$emit('show-alert', 'alert-success')
                this.name = null;
                this.last_name = null;
            } else {
                this.$emit('show-alert', 'alert-warning')
            }
        }
        

    }
    

}

</script>
<style>
    form{
        padding: 1rem 2rem; 
    }
    form div{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
    form button{
        margin-top: 3vh;
        width: 10%;
    }
    @media (max-width: 768px) {
        form button{
            width: 50%;
            margin-top: 3vh;
        }
        form{
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        form div{
            width: 50%;
        }
        form div input{
            width: 100%;
        }
    }
</style>
