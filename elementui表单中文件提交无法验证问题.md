#表单中文件上传没有办法通过普通的rules进行验证


##解决方法：利用<el-upload>中的on-change事件来改变prop的值，再对单项进行验证来达到最终效果。


eg.


_html_

`<el-form-item label="首次提取统计数据" prop="statisticData">
  <el-upload action="12" ref="statisticData0" :auto-upload="false" :before-upload="file=>docUploadFun('searchData','statisticalDataFile',file)" :on-change="file=>docChange('statisticData',file)" accept="application/msword,application/vnd.openxmlformats-officedocument.wordprocessingml.document">
    <el-button size="small" type="primary">点击上传</el-button>
      <div slot="tip" class="el-upload__tip">只能上传excel文件</div>
  </el-upload>
</el-form-item>`

_js_

`docChange:function(item,file){
  this.buryPointValidationForm[item]=file.name;
  this.$refs.buryPointValidationForm.validateField(item);	//验证文件上传
}`,
