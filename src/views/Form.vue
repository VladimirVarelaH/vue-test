<template>
  <div >
    <h1>Full Name: {{ fullName }}</h1>
    <Alert :text="alert_text" :alertClass="alert_class" :flag="show_alert"/>
    <Form name="Vladimir" @data-submited="getData" @show-alert="showAlert"/>
  </div>
</template>

<script>
  import Form from '@/components/Form.vue';
  import Alert from '@/components/Alert.vue';

  export default {
    name: 'FormIndex',
    components: {
      Form,
      Alert
    },

    data: ()=>({
      count: 0,
      name: '',
      last_name: '',
      show_alert: false,
      alert_text: '',
      alert_class: ''
    }),

    methods: {
      addOne: function(num){
        this.count += num;
      },
      getData: function(data){
        this.name = data.name;
        this.last_name = data.last_name;
      },
      showAlert: function(alert_class){
        if (alert_class === 'alert-success'){
          this.alert_text= "Todo en orden";
          this.alert_class= alert_class;
          this.show_alert = true;
        } else if (alert_class === 'alert-warning'){
          this.alert_text= "Por favor revisa los datos";
          this.alert_class= alert_class;
          this.show_alert = true;
        }
      }
    },
    computed: {
        fullName(){
          if (this.name && this.last_name){
              return (this.name + ' ' +this.last_name);
          } else {
              return ('');
          }
        }
    } 

  }
</script>

<style>
  
</style>
