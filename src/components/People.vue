<template>
	<div class="people">
		<div>
			<el-row>
			  <el-col :span="6"><div class="grid-content bg">男士</div></el-col>
			  <el-col :span="6"><div class="grid-content bg-purple-light">￥15</div></el-col>
			  <el-col :span="12"><div class="grid-content bg-purple">
			  	<el-input-number size="mini" v-model="num1" @change="clickNum"  
			  		:min="0" :max="10000" label="描述文字">
			  	</el-input-number>
			  </div></el-col>
           </el-row>
		</div>
		<br />
		
		<div>
			<el-row>
			  <el-col :span="6"><div class="grid-content bg-purple">女士</div></el-col>
			  <el-col :span="6"><div class="grid-content bg-purple-light">￥15</div></el-col>
			  <el-col :span="12"><div class="grid-content bg-purple">
			  	<el-input-number size="mini" v-model="num2" @change="clickNum" :min="0" :max="10000" label="描述文字"></el-input-number>
			  </div></el-col>
			  <el-col :span="17"><div class="grid-content"></div></el-col>
           </el-row>
		</div>
		<br />
		
		<div>
			<el-row>
			  <el-col :span="6"><div class="grid-content bg-purple">儿童</div></el-col>
			  <el-col :span="6"><div class="grid-content bg-purple-light">￥7</div></el-col>
			  <el-col :span="12"><div class="grid-content bg-purple">
			  	<el-input-number size="mini" v-model="num3" @change="clickNum" :min="0" :max="10000" label="描述文字"></el-input-number>
			  </div></el-col>
           </el-row>
		</div>
	</div>
</template>

<script>
	export default{
	 data() {
      return {
        num1: 0,num2: 0,num3: 0,
        props:{
        	source:{
        		type:String,
			    default:function(){
			    return ""
      }
        	}
        }
      }
    },
     methods: {
      clickNum() {
            //1、childFn 组件方法名，父组件中用childFn方法接收子组件中的数据；2、num1是传递给父组件的数据
            this.$emit('childFn', this.num1,this.num2,this.num3)
       }
    }
	}
</script>

<style>
	.people{
		width: 400px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04);
	}
</style>