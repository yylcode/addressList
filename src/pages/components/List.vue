<template>
	<div id="list">
		<ul class="list_user">
			<li v-for="item in userdata">
				<p>{{item.index}}</p>
				<ul>
					<li v-for="user in item.user">{{user.name}}</li>
				</ul>
			</li>
			 
		</ul>
		<ul class="list_index">
			<li>A</li>
			<li>B</li>
		</ul>
	</div>
</template>
<script type="text/javascript">
	export default{
		name:'List',
		props:{
			'userdata':{
				type:Array,
				default:function(){
					return [];
				}
			}
		}
	}
</script>
<style type="text/css" media="screen">
	#list{
		 
		position: relative;
		top: 40px;
	}
	.list_user p{
		background: #ccc;
		padding: 10px;
	}
	.list_user ul li{
		height: 50px;
		line-height: 50px;
		border-bottom: 1px solid #ccc;
		padding-left: 10px;
	}
	.list_index{
		position: fixed;
		right: 10px;
		top: 50%;
		font-size: 20px;
		list-style: none;
	}
</style>