<template>
	<div id="list">
		<ul class="list_user" ref="listUser" @touchmove="bMove=true">
			<li v-for="item in userdata">
				<p>{{item.index}}</p>
				<ul>
					<li @touchend="showTel(user.tel)" v-for="user in item.user">{{user.name}}</li>
				</ul>
			</li>
			 
		</ul>
		<ul class="list_index" ref="listIndex">
			<li @touchstart="setScroll" v-for="item in userdata">{{item.index}}</li>
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
		data:function(){
			return {
				bMove:false
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
			},
			showTel:function(tel){
				if(!this.bMove){
					//console.log(tel);
					this.$emit('changeEvents',tel);
				}else{
					this.bMove=false;
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
		top: 12%;
		font-size: 14px;
		font-family: "宋体";
		padding: 5px;
		list-style: none;
	}
	.list_index li{
		margin-top: 2px;
	}
</style>