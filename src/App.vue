<template>
	<div>
		<User v-if="showUser"/>
		<Post v-else-if="showUserPost" :user="user"/>
	</div>
</template>

<script>
	import User from '@/components/User';
	import Post from '@/components/Post';
	export default {
		name: 'App',
		components: {
			User,
			Post
		},
		data(){
			return {
				user : 0,
				showUser : true,
				showUserPost : false	
			}
		},
		methods:{
			
			
		},
		created(){
			
		}
	}
</script>

<style>

</style>
