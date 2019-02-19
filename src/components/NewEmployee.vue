<template>
    <div id="newEmployee">
        <h3>New Employee</h3>
        <div class="row">
            <form @submit.prevent="saveEmployee" class="col s12">
                <div class="row">
                    <input type="text" v-model="employee_id" required>
                    <label> Employee Id</label>
                </div>
                <div class="row">
                    <input type="text" v-model="name" required>
                    <label> Name</label>
                </div>
                <div class="row">
                    <input type="text" v-model="dept" required>
                    <label> Department</label>
                </div>
                <div class="row">
                    <input type="text" v-model="position" required>
                    <label> Position</label>
                </div>
                <button type="submit" class="btn">Create</button>
                <router-link to="/" class="btn grey">Cancel</router-link>
            </form>
        </div>

    </div>
</template>

<script>
    import db from './firebaseInit'
    export default {
        name: 'NewEmployee',
        data() {
            return {
                employee_id: null,
                name: null,
                dept: null,
                position: null
            }
        },
        methods: {
            saveEmployee() {
                db.collection('employees').add({
                    employeeId: this.employee_id,
                    name: this.name,
                    dept: this.dept,
                    position: this.position
                })
                .then(docRef => {
                    this.$router.push('/')
                })
                .catch(err => console.log(err))
            }
        }
    }
</script>

<style scoped>

</style>
