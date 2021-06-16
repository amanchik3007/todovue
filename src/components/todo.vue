<template>
  <div> 
        <div>
            <input type="text" v-model="input_title"> 
            <input type="text" v-model="input_about">
            <button @click="addTolist()"> click</button>         
        </div> 
        <div>
            <div v-for="(block, i) in list" :key="block.id">
                <div> 
                    {{block.title}}
                    <button @click="redact(i)"> redact </button>
                    <button @click="removefromlist(i)">close</button>
                </div>
                {{block.about}}
            </div>
        </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            input_title: "",
            input_about: "",
            current: null,
            list:[
                {
                    id: 1,
                    title: "title 1",
                    about: "about 1"
                }
            ]
        }
    }, 
    methods:{
        addTolist() {
            if(this.current) {
                this.list[this.list.findIndex(x => x.id == this.current)] = {
                    id: this.current,
                    title: this.input_title,
                    about: this.input_about,
                }
            } else {
            this.list.push({
                id: this._uid,
                title: this.input_title,
                about: this.input_about,
            
            })
            }
            this.input_title = ""
            this.input_about = ""
            this.current = null
        },
        removefromlist(index){
            this.list.splice(index,1)
        },
        redact(i){
            this.input_title = this.list[i].title
            this.input_about = this.list[i].about
            this.current = this.list[i].id
        }
    }
}
</script>

<style scoped>

</style>