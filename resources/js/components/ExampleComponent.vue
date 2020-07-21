<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Категории</div>

                    <div class="card-body">
                        <select>
                            <option value="">Выберите категорию</option>
                            <option v-for="category in getCategories" 
                                    :value="category.id"
                                    :key="category.id"
                            >
                            {{ category.name }}
                            </option>
                        </select>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            this.$store.dispatch('ajaxCategoriesFromDB')
        },
        computed: {
            getCategories() {
                return this.$store.getters.getCategories
            }
        }
    }
</script>
