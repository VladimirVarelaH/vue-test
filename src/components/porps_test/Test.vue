<template>
    <div>
        <section>
            <!-- <div>
                <label for="">Nombre</label>
                <input @onchange="write" type="text" name="name" id="">
                <label for="">Email</label>
                <input type="text" name="last_name" id="">
                <label for="">Message</label>
                <textarea type="text" name="" id=""></textarea>
                <button>Send</button>
            </div> -->
            <!-- <div>
                <h1>Name: {{name}}</h1>
            </div> -->
        </section>
        <section>
            <button @click="addOne(-1)">-</button>
            <button @click="addOne(1)">+</button>
        </section>
    </div>
</template>

<script>
export default {
    name: 'Form',
    
    props: {
        name: {
            type: String,
            default: 'User'
        }
    },
    data: ()=>({
        counter: 0,
    }),

    methods: {
        addOne: function (num) {
            this.$emit('add-one', num);
        },
        write: function(event){
            this.name = event.target.value;
        }

    } 

}

</script>
<style>

</style>
