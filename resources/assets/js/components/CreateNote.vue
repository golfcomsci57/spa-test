<template>
    <div class="note-form">
        <div class="component-header">Create A new Note</div>
        <form @submit.prevent="add">
            <input v-model="title">
            <button type="submit">Create</button>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'CreateNote',
        data() {
          return {
              title: ''
          }
        },
        mounted() {
        },
        methods: {
            add() {
                this.$store.dispatch('add', this.title);
                this.$router.push('/list');
                flash('Note Created.', 'success');
            }
        }
    }
</script>