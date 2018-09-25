<template>
	<div class="header"> 
		<div class="content">
			<button>返回</button>
			通讯录
			<button>主页</button>
		</div>
		
	</div>

</template>
<script>
	export default{
		name:'Header'
	}
</script>
<style>
	.header{
		height: 40px;
		width: 100%;
		position: fixed;
		z-index: 9;
	}
	.content{
		height: 40px;
		width: 100%;
		background: grey;
		line-height: 40px;
		position: absolute;
		top: 0;
		text-align: center;
		font-size: 20px;
		color: white;
	}
	.content button{
		height: 38px;
		position: absolute;
		padding: 5px;
		top: 1px;
		font-weight: bold;
		color: black;
		background: white;
	}
	.content button:nth-child(1){
		left: 1px;
	}
	.content button:nth-child(2){
		right: 1px;
	}
</style>