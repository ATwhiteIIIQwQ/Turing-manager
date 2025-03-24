<template>
    <div>
        <el-table :data="tableData" style="width: 100%">
        <el-table-column prop="studentName" label="姓名" width="180"></el-table-column>
        <el-table-column prop="studentAge" label="年龄" width="180"></el-table-column>
        <el-table-column prop="studentHobby" label="爱好" width="180"></el-table-column>
        <el-table-column prop="studentSex" label="性别" width="180"></el-table-column>
        <el-table-column prop="studentBirthday" label="出生日期" width="180"></el-table-column>
        </el-table>
    </div>
</template>

<script>
    import { listStudent, getStudent, delStudent, addStudent, updateStudent, listStudentByAge } from "@/api/system/student";

    export default {
        data() {
            return {
                tableData: [],
            };
        },
        
        created() {
            this.getList();
        },

        methods: {
            getList() {
                listStudentByAge({studentAge:10}).then(response => {
                    console.log(response);
                    this.tableData = response.rows;
                });
            },
        }
    }
</script>