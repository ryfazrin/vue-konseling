<template>
  <CModal
    title="Modal title"
    color="warning"
    :show.sync="showModal"
    >
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
        quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
        consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
        cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
        proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </CModal>
</template>

<script>
export default {
    name: 'AddModal',
    data() {
        return {
            showModal: false
        }
    },
    methods: {
        setModal(stat) {
            this.showModal = stat
        }
    },
}
</script>

<style>

</style>