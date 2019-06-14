<template>
    <div>
        <input type="text" v-model="messageChild" />        
        <button type="button" @click.prevent="submit">Submit</button>
    </div>
</template>
<script>
export default {
    data(){
        return {
            messageChild: 'child message!'
        }
    },
    methods:{
        submit: function(){
            this.$emit('clicked', this.messageChild)
        }
    }
}
</script>