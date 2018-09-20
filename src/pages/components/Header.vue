<template>
	<div class="content"> 
		<button>返回</button>
		通讯录
		<button>主页</button>

	</div>
</template>
<script>
	export default{
		name:'Header'
	}
</script>
<style>
	.content{
		height: 40px;
		background: grey;
		line-height: 40px;
		text-align: center;
		font-size: 20px;
		color: white;
	}
	.content button{
		height: 38px;
		position: fixed;
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