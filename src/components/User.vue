<template>
    <div class="container mt-3">
		<div class="row">
			<div class="col-md-10 col-md-offset-2">
				<table class="table">
					<thead>
						<tr class="table-primary">
							<th>#</th>
							<th>Name</th>
							<th>Username</th>
							<th>Email</th>
							<th>Address</th>
							<th>Phone</th>
                            <th></th>
						</tr>
					</thead>
					<tbody>
						<tr v-for="user in users" :key="user.id">
							<th>{{user.id}}</th>
							<td>{{user.name}}</td>
							<td>{{user.username}}</td>
							<td class="table-success">{{user.email}}</td>
							<td>{{user.address.street}} {{user.address.suite}} {{user.address.city}} - {{user.address.zipcode}}</td>
							<td>{{user.phone}}</td>
                            <td>
                                <button class="btn btn-sm btn-success">
                                    <i class="far fa-clipboard"></i>
                                </button>
                            </td>
						</tr>
					</tbody>
				</table>
			</div>
		</div>
	</div>
</template>
<script>
    const BASE_URL = "https://jsonplaceholder.typicode.com";
	export default {
		name: 'User',
		components: {
			
		},
		data(){
			return {
				users: []
			}
		},
		methods:{
			getUsers(){
				fetch(`${BASE_URL}/users`)
					.then(response 	=> response.json())
					.then(json 		=> this.users = json)
			}
		},
		created(){
			this.getUsers()
		}
	}
</script>