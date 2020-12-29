<template>
	<div class="record">
		<div class="record1">
		<el-row type="flex" class="row-bg" justify="space-around">
		  <el-col :span="6"><div class="grid-content bg-purple">男士：1</div></el-col>
		  <el-col :span="6"><div class="grid-content bg-purple-light">女士：1</div></el-col>
		  <el-col :span="6"><div class="grid-content bg-purple">儿童：1</div></el-col>
		</el-row>
		</div>
		
		<div class="record2">
			<el-row>
			  <el-col :span="24"><div class="grid-content bg-purple"></div></el-col>
			</el-row>
		</div>
	</div>
</template>

<script>
</script>

<style lang="less">
	.record{
		width: 400px;
		height: 400px;
		margin-top: 0px;
		.record1{
			width: 400px;
			height: 30px;
			padding-top: 20px;
			/*margin-top: 20px;*/
			box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04);
	     }
	    .record2{
	    	width: 390px;
			height: 350px;
			padding-top: 10px;
			padding-left: 10px;
			box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04);
	    }
	}
	
</style>