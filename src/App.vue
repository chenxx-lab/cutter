<template>
  <div id="app">
  	<People @childFn="parentFn" :source="source"></People>
  	
  	<div class="record">
		<div class="record1">
		<el-row type="flex" class="row-bg" justify="space-around">
		  <el-col :span="6"><div class="grid-content bg-purple">男士：{{manNumber}}</div></el-col>
		  <el-col :span="6"><div class="grid-content bg-purple-light">女士：{{womanNunber}}</div></el-col>
		  <el-col :span="6"><div class="grid-content bg-purple">儿童：{{childNunber}}</div></el-col>
		</el-row>
		</div>
		
		<div class="record2">
			<el-row>
			  <el-col :span="24"><div id = "manp" class="grid-content bg-purple" :manNum="manNum">
			    <!--//{{manNum}}-->
			    <p>{{zs}}</p>
			    <!--<p>{{zNum}}</p>-->
			  </div></el-col>
			</el-row>
		</div>
	</div>
 
  </div>
</template>

<script>
	import People from './components/People'
	export default{
		data(){
			return{
//				manNum_max:0,
//				womanNum_max:0,
				manNumber:0,
				womanNunber:0,
				childNunber:0,
				zNum:[],
				manNum:[],
				womanNum:[],
				childNum:[],
				count_num:33,
				count1:0,
				count2:0,
				count3:0,
				zs:"",
				source:{
            man:'N034',
            woman:'V034',
            child:'E034',
            manPrice:15,
            womanPrice:15,
            childPrice:7
          }
			}
		},
		methods:{
			parentFn(num1,num2,num3) {
        this.manNumber = num1
        this.womanNunber=num2
        this.childNunber=num3
        
//      if(num1 > this.manNum_max){
//      	this.manNum_max = num1;
//      }
//      if(num2 > this.womanNum_max){
//      	this.womanNum_max = num2;
//      }
        
        //男人
        if(this.count1 < num1){
        	this.count_num ++;
        	this.manNum.splice(num1,0,'N0'+this.count_num);
        	this.count1 = num1;
        }
        if(this.count1 > num1){
        	this.manNum.splice(0,1);
        	this.count1 = num1;
        }
//      var st1 = "";
//      for(var i = 0; i < this.manNum.length;i++){
//      	st1 += this.manNum[i].toString() + " , ";
//      }
        
        //女人
        if(this.count2 <num2){
        	this.count_num ++;
        	this.womanNum.splice(num2,0,'V0'+this.count_num);
        	this.count2 = num2;
        }
        if(this.count2 > num2){
        	this.womanNum.splice(0,1);
        	this.count2 = num2;
        }
//      var st2 = "";
//      for(var i = 0; i < this.womanNum.length;i++){
//      	st2 += this.womanNum[i].toString() + " , ";
//      }
//      this.zs = st1 + st2; 

        //儿童
         if(this.count3 <num3){
        	this.count_num ++;
        	this.childNum.splice(num3,0,'C0'+this.count_num);
        	this.count3 = num3;
        }
        if(this.count3 > num3){
        	this.childNum.splice(0,1);
        	this.count3 = num3;
        }
   
        this.zNum = [].concat(this.womanNum,this.manNum,this.childNum);
        
        this.zNum = this.zNum.sort(function(a,b){
        	var a1 = a.slice(2);
        	var b1 = b.slice(2);
        	return a1-b1;
        });
        var st = "";
        var i;
        for(i = 0; i < this.zNum.length-1;i++){
        	st += this.zNum[i].toString() + " , ";
        }
        st += this.zNum[i].toString();
        this.zs = st;
     }
		
		},
		components:{
			People
		}
	}
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
			height: auto;
			padding-top: 10px;
			padding-left: 10px;
			box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04);
	    }
	}
	
</style>
