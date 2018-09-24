<template>
	<div id="list">
		<ul class="list_user" ref="listUser">
			<li v-for="item in userdata">
				<p>{{item.index}}</p>
				<ul>
					<li v-for="user in item.user">{{user.name}}</li>
				</ul>
			</li>
			 
		</ul>
<<<<<<< HEAD
		<ul class="list_index">
			<li v-for="item in userdata">{{item.index}}</li>
			
=======
		<ul class="list_index" ref="listIndex">
			<li @touchstart="setScroll" v-for="item in userdata">{{item.index}}</li>
>>>>>>> home-list
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
		},
		methods:{
			
			setScroll:function(ev){
				var aP=this.$refs.listUser.getElementsByTagName('p');
				for(var i=0;i<aP.length;i++){
					if (aP[i].innerHTML==ev.target.innerHTML) {
						document.documentElement.scrollTop=aP[i].offsetTop;
					}
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
<<<<<<< HEAD
		top: 16%;
		font-size: 12px;
=======
		top: 12%;
		font-size: 14px;
		font-family: "宋体";
		padding: 5px;
>>>>>>> home-list
		list-style: none;
		padding: 4px;
		line-height: 19px;
		color: black;
		opacity: 0.6;
	}
	.list_index li{
		margin-top: 5px;
	}
</style>