<!--  -->
<template>
<div class='adminUser'>
    <!-- <Public></Public> -->
    <div class="adminUsermain">
        <el-row>
        <!-- usertitle -->
        <el-col :span="20"><div class="grid-content bg-purple-dark usertitle">管理员列表</div></el-col>

        <!-- 中间位置 实现添加搜索管理员功能 usermiddle -->
        <el-col :span="20">
            <div class="grid-content bg-purple-dark usermiddle">
                <!-- 添加管理员按钮 -->
                <el-button type="primary" plain>添加管理员</el-button>
                <!-- 搜索管理员功能 -->
                <div class="add-right float_right">
                    <!-- 输入管理员名字搜索 含v-model -->
                    <el-input class="middleinput"
                        placeholder="管理员用户名"
                        v-model="input"
                        clearable>
                    </el-input>
                    <!-- 搜索按钮 需添加功能 -->
                    <el-button type="primary" class="middlebutton">搜索</el-button>
                </div>
            </div>
        </el-col>
        <!-- 添加搜索功能结束 -->

        <!-- 显示管理员表格 usertable -->
        <el-col :span="20">
            <div class="grid-content bg-purple-dark usertable">
                <el-table
                    :data="tableData"
                    border
                    style="width: 100%">
                    <el-table-column
                        prop="date"
                        label="ID"
                        width="60"
                        align="center">
                    </el-table-column>
                    <el-table-column
                        prop="name"
                        label="管理员名称"
                        width="160"
                        align="center">
                    </el-table-column>
                    <el-table-column 
                        prop="address"
                        label="管理员真实姓名"
                        width="160"
                        align="center">
                    </el-table-column>
                    <el-table-column 
                        prop="address"
                        label="管理员角色"
                        width="161"
                        align="center">
                    </el-table-column>
                    <el-table-column 
                        prop="address"
                        label="最后登录IP"
                        width="161"
                        align="center">
                    </el-table-column>
                    <el-table-column 
                        prop="address"
                        label="最后登录时间"
                        width="161"
                        align="center">
                    </el-table-column>
                    <el-table-column 
                        label="状态"
                        width="80"
                        align="center">
                        <!-- 按钮 -->
                        <el-button type="success" size="mini">正常</el-button>
                    </el-table-column>
                    <el-table-column 
                        label="操作"
                        width="161"
                        align="center">
                        <el-button type="primary" size="mini">编辑</el-button>
                        <el-button type="danger" size="mini">删除</el-button>
                    </el-table-column>
                </el-table>
            </div>
        </el-col>
        <!-- 显示管理员表格结束 -->

        <!-- 底部 分页栏开始 -->
        <el-col :span="20">
            <div class="grid-content bg-purple-dark">
                <div class="block float_right">
                    <el-pagination
                    @size-change="handleSizeChange"
                    @current-change="handleCurrentChange"
                    :current-page="currentPage4"
                    :page-sizes="[10, 25, 50, 100]"
                    :page-size="10"
                    layout="total, sizes, prev, pager, next, jumper"
                    :total="4">
                    </el-pagination>
                </div>
            </div>
        </el-col>
        <!-- 底部 分页兰结束 -->
        </el-row>
    </div>
</div>
</template>

<script>
//这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
//例如：import 《组件名称》 from '《组件路径》';
import Public from "../public"
export default {
//import引入的组件需要注入到对象中才能使用
components: {
    Public,
},
data() {
//这里存放数据
return {
    input: '',
    tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }],
    currentPage1: 5,
    };
},
//监听属性 类似于data概念
computed: {},
//监控data中的数据变化
watch: {},
//方法集合
methods: {
    handleSizeChange(val) {
    console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
    console.log(`当前页: ${val}`);
    }
},
//生命周期 - 创建完成（可以访问当前this实例）
created() {

},
//生命周期 - 挂载完成（可以访问DOM元素）
mounted() {

},
beforeCreate() {}, //生命周期 - 创建之前
beforeMount() {}, //生命周期 - 挂载之前
beforeUpdate() {}, //生命周期 - 更新之前
updated() {}, //生命周期 - 更新之后
beforeDestroy() {}, //生命周期 - 销毁之前
destroyed() {}, //生命周期 - 销毁完成
activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
}
</script>
<style  lang='less' scoped>
.adminUser {
    height: 100%;
    .adminUsermain {
        padding: 20px;
        .usertitle {
            padding: 10px;
            height: 38px;
            margin: 16px 0;
            color: #ccc;
            border-bottom: 1px dashed #ccc;
            }
        .usermiddle {
            padding-bottom: 10px;
            .add-right {
                .middleinput {
                    width: 200px;
                    margin-right: 5px;
                } 
            }
        }
        .usertable {
            margin-bottom: 20px;
        }
    }
}
</style>