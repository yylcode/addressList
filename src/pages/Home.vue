<template>
	<div>
		<home-header></home-header>
		<home-list :userdata="userdata"></home-list>
		<div class="space"></div>
	</div>
</template>
<script>
	import HomeHeader from './components/Header'
	import HomeList from './components/List'
	import axios from 'axios'
	export default{
		name:'Home',
		data(){
			return{
				userdata:[]
			}
		},
		components:{
			HomeHeader,
			HomeList
		},
		mounted(){
			this.getUser()
		},
		methods:{
			getUser(){
				axios.get('/api/user.json').then(this.getUserSucc)
			},
			getUserSucc(res){
				console.log(res.data)
				 if (res.data.ret==true) {
				 	this.userdata=res.data.data;
				 }
			}
		}

	}
</script>
<style>
	*{
		padding: 0;
		margin: 0;
		border: 0;
	}
	.space{
		height: 500px;
	}
</style>