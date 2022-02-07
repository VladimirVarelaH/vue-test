<template>
    <div v-show="flag" :class="alert_class" role="alert">
        {{text}}
    </div>
</template>

<script>
export default {
    name: 'Alert',
    
    props: {
        text: {
            type: String,
            required: true,
        },
        alertClass: {
            type: String,
            required: true,
            default: ""
        },
        flag:{
            type: Boolean,
            default: false
        }
    },
    data: ()=>({
        local_class: "alert "
    }),

    methods: {

    },
    computed: {
        alert_class(){
            return this.local_class + this.alertClass;
        }
    }
    

}
</script>

