<!--
 * @moduleName: 测试el-tree-select
 * @Author: dawdler
 * @Date: 2018-12-19 14:03:03
 * @LastModifiedBy: dawdler
 -->
<template>
    <div id="app">
        <el-form label-width="120px">
            <el-row :gutter="20">
                <el-col :span="12">
                    <el-form-item label="单选">
                        <TreeSelect :isSingle="true" :params="{ clickParent: false }"></TreeSelect>
                    </el-form-item>
                </el-col>
                <el-col :span="12">
                    <el-form-item label="多选">
                        <TreeSelect></TreeSelect>
                    </el-form-item>
                </el-col>
                <el-col :span="12">
                    <el-form-item label="弹框关闭调试">
                        <el-select multiple v-model="test" placeholder="请选择" @change="_selectChange">
                            <el-option v-for="item in testData" :key="item" :label="item" :value="item" />
                        </el-select>
                        <div>
                            测试焦点触发
                            <svg>
                                <circle cx="100" cy="50" r="40" stroke="black" stroke-width="2" fill="red" />
                            </svg>
                        </div>
                    </el-form-item>
                </el-col>
            </el-row>
        </el-form>
    </div>
</template>
<script>
import TreeSelect from './treeSelect';
export default {
    name: 'App',

    components: { TreeSelect },
    data() {
        return {
            test: '',
            testData: ['test1', 'test2']
        };
    },
    created() {},
    mounted() {},
    methods: {
        // 下拉框修改
        _selectChange(val) {
            console.log(val, '<-select change');
        }
    }
};
</script>
<style lang="less">
#app {
    display: flex;
    justify-content: space-between;
    width: 100%;
}
.el-select {
    width: 300px;
}
</style>
