<template>
    <div class="col-sm-6 col-md-6 col-lg-6" >
        <div class="card shadow-sm">
            <div class="card-body quote">
                <form>
                    <label>Quote</label>
                    <textarea 
                    name="" 
                    class="form-control" 
                    id="" 
                    style="width:100%" 
                    rows="6" 
                    placeholder="New Quote..."
                    v-model="quote"></textarea>
                    <div class="d-flex justify-content-center my-3">
                        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                quote: ''
            }
        },
        methods:{
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>

</style>