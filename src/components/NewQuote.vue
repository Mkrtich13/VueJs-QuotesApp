<template>
    <div class="row">
        <form action="">
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" cols="30" rows="3" v-model="quote"></textarea>
            </div>
            <div class="text-right col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button @click.prevent="createNew" class="btn btn-primary">
                    Valider
                </button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ""
            }
        },
        methods: {
            createNew() {
                if(this.quote.trim() !== "") {
                    this.$emit("quoteAdded", this.quote);
                    this.quote = "";
                }
            }
        }
    }
</script>

<style>

</style>