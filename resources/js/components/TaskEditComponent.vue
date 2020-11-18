<template>
    <div class="container">
        <div class="col-sm-6">
            <form>
                <div class="form-group row">
                    <lable for="id" class="col-sm-3 col-form-label">ID</lable>
                    <input type="text" class="col-sm-9 form-control" id="title">
                </div>
                <div class="form-group row">
                    <lable for="content" class="col-sm-3 col-form-label">Content</lable>
                    <input type="text" class="col-sm-9 form-control" id="content">
                </div>
                <div class="form-group row">
                    <lable for="person-in-charge" class="col-sm-3 col-form-label">Person In Charge</lable>
                    <input type="text" class="col-sm-9 form-control" id="person-in-charge">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        taskId: String
    }
}
</script>
