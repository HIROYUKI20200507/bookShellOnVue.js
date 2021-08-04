<template>
    <div>
        ブックエディット
        {{ book.title }}
    </div>
</template>

<script>
export default {
    name: 'BookEdit',
    props: {
        books: Array
    },
    data() {
        return {
            book: '',
        }
    },
    beforeRouteEnter(to, from, next) {
        next(vm => {
            vm.$nextTick(() => {
                vm.book = vm.books[vm.$route.params.id]
            })
        })
    }
}
</script>

<style>

</style>