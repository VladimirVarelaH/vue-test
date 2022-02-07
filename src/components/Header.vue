<template>
    <section>
        <header>
                    
            <img :src="Logo" height="50vh"/>

            <div class="ham">
                <button type="button" :class="buttonPros.btnClass" @click="setOptions">
                    {{buttonPros.text}}
                </button>
            </div>
            <nav class="opt">
                <router-link style="text-decoration: none" :to="{ path: '/' }">
                    <div >
                        <span >Inicio</span>
                    </div>
                </router-link>
                <router-link style="text-decoration: none" :to="{ path: '/form' }">
                    <div >
                        <span >Formulario</span>
                    </div>
                </router-link>

            </nav>
        </header>
        <nav class="ham-opt" v-show="showOptions">
            <div>
                <router-link style="text-decoration: none" :to="{ path: '/' }">
                    <div  @click="setOptions">
                        <span >Inicio</span>
                    </div>
                </router-link>
            </div>
            <div>
                <router-link style="text-decoration: none" :to="{ path: '/form' }">
                    <div  @click="setOptions">
                        <span >Formulario</span>
                    </div>
                </router-link>
            </div>
        </nav>

    </section>
</template>

<script>
import Logo from "@/assets/logo.png";
import Ham from "@/assets/bars-solid.svg";

export default {
    name: 'MyHeader',
    data: () => ({
    Logo,
    Ham,
    showOptions: false
    }),
    props: {
        name: {type: String},
        img_src: {type: String}
    },
    methods: {
        setOptions: function (){
            this.showOptions = !this.showOptions;
        }
    },
    computed: {
        buttonPros(){
            if (this.showOptions){
                return (
                    {btnClass: "btn btn-danger", text: "X"}
                )
            }else{
                return (
                    {btnClass: "btn btn-success", text: "Menu"}
                )
            }
        }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #000;
    color: #fff;
    margin: 0;
    padding: 0 1vw;
}
.opt{
    width: 15%;
    display: flex;
    justify-content: space-around;
}
.ham{
    display: none;
}
.opt a {
  color: #42b983;
  text-decoration: none;
  text-transform: uppercase;
}
.ham-opt div{
    width: 100%;
    background-color: #f4f4f4;
    text-align: center;
    border-bottom: 1px solid #cecccc;
}


@media (max-width: 1024px) {
    .opt{
        width: 20%;
    }
    .opt a{
        text-transform: capitalize;
    }
}
@media (max-width: 768px) {
    .opt{
        display: none;
    }
    .ham{
        display: block;
    }
    .ham-opt a{
        color: #42b983;
        text-decoration: none;
        text-transform: capitalize;
    }
    .ham-opt{
        padding: 0 0 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

}
</style>
