<template>    
    <div class="row">
        <div class="col-md-12">

            <div class="card mb-3 mt-3" v-for="item in list">                
                <router-link class="card-header" :to="{name: 'post', params:{slug: item.slug}}" v-text="item.title">

                </router-link>
                <div class="card-body">
                    <p class="card-text" v-text="item.excerpt"></p>
                </div>
            </div>

            <infiniteLoading @infinite="infiniteHandler">
                <div slot="no-more">---</div>
                <div slot="spinner">Cargando...</div>
                <div slot="no-results">Sin resultados</div>
            </infiniteLoading>
        </div>
    </div>    
</template>

<script>
    export default {
        data(){
            return {
                list : [],
                page:0
            };
        },
        methods: {
            infiniteHandler($state){
                this.page++;
                let url = 'http://localhost:8000/api/posts?page='+this.page;

                axios.get(url).then(response => {
                    let posts = response.data.data;

                    if(posts.length){
                        this.list = this.list.concat(posts);
                        $state.loaded();
                    }
                    else{
                        $state.complete();
                    }
                });
            }
        }

    }
</script>
