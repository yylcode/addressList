<template>
	<div :class="className">
		<div class="alert_content">
			<div class="alert_title">
				{{alertTitle}}
			</div>
			<div class="alert_body">
				{{alertBody}}
			</div>
			<div class="alert_btn">
				<button>确认</button>
				<button @click="exit">取消</button>
			</div>
		</div>
	</div>
</template>
<script>
	export default{
		name:'Alert',
		props:{
			alertTitle:String,
			alertBody:String,
			className:String
		},
		methods:{
			exit:function(){
				this.$emit("changeAlert");
			}
		}
		
	}
</script>
<style type="text/css" media="screen">
	.alert{
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.5);
		position: fixed;
		top: 0;
		left: 0;
		z-index: 20;
		display: flex;
	}
	.noAlert{
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, 0.5);
		position: fixed;

		top: 0;
		left: 0;
		z-index: 20;
		display: none;
	}
	.alert_content{
		width: 200px;
		height: 150px;
		background: white;
		border-radius: 5px;
		margin: auto;
	}
	.alert_title{
		padding: 5px;
		border-bottom: 1px solid #ccc;
		text-align: center;
	}
	.alert_body{
		 height: 50px;
		 line-height: 50px;
		 text-align: center;
	}
	.alert_btn{
		text-align: center;
		
	}
	.alert_btn button{
		height: 30px;
		width: 60px;
		margin-top: 10px;
		border-radius: 3px;
		border: 1px solid #ccc;
	}
</style>