<template>
	<div>
		<home-header></home-header>
		<home-list :userdata="userdata" @changeEvents="changeEvents"></home-list>
		<home-alert @changeAlert="changeAlert" :className="className" :alertTitle="alertTitle" :alertBody="alertBody">
		</home-alert>
		
	</div>
</template>
<script>
	import HomeHeader from './components/Header'
	import HomeList from './components/List'
	import HomeAlert from './components/Alert'
	import axios from 'axios'
	export default{
		name:'Home',
		data(){
			return{
				userdata:[],
				alertTitle:'呼叫',
				alertBody:'110',
				className:'noAlert'
			}
		},
		components:{
			HomeHeader,
			HomeList,
			HomeAlert
		},
		mounted(){
			this.getUser()
		},
		methods:{
			getUser(){
				axios.get('/api/user.json').then(this.getUserSucc)
			},
			getUserSucc(res){
				// console.log(res.data)
				 if (res.data.ret==true) {
				 	this.userdata=res.data.data;
				 }
			},
			changeEvents:function(tel){
				this.className="alert";
				this.alertBody=tel;
			},
			changeAlert:function(){
				this.className="noAlert";
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
	

</style>