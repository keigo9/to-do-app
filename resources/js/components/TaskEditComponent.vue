<template>
    <div class="container">
        <div class="col-sm-6">
            <form v-on:submit.prevent="submit">
                <div class="form-group row">
                    <lable for="id" class="col-sm-3 col-form-label">ID</lable>
                    <input type="text" class="col-sm-9 form-control" id="id" v-model="task.id">
                </div>
                <div class="form-group row">
                    <lable for="title" class="col-sm-3 col-form-label">title</lable>
                    <input type="text" class="col-sm-9 form-control" id="title" v-model="task.title">
                </div>
                <div class="form-group row">
                    <lable for="content" class="col-sm-3 col-form-label">Content</lable>
                    <input type="text" class="col-sm-9 form-control" id="content" v-model="task.content">
                </div>
                <div class="form-group row">
                    <lable for="person-in-charge" class="col-sm-3 col-form-label">Person In Charge</lable>
                    <input type="text" class="col-sm-9 form-control" id="person-in-charge" v-model="task.person_in_charge">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        taskId: String
    },
    data: function () {
        return {
            task: {}
        }
    },
    methods: {
        gatTask() {
            axios.get('/api/tasks/'+this.taskId)
                .then((res) => {
                    this.task = res.data;
                })
        },
        submit() {
            axios.put('/api/tasks/'+this.taskId,this.task)
                .then((res) => {
                    this.$router.push({name:'task.list'})
                });
        }
    },
    mounted() {
        this.getTask();
    }
}
</script>
