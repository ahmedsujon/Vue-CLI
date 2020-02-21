<template>
	<div class="Hook">
		<h1>All Posts</h1>
		<div v-for="post in posts" :key="post.id">
			<h3>{{ post.id }}</h3>
			<h3>{{ post.title }}</h3>
			<p>{{ post.body }}</p>
		</div>
	</div>
</template>

<script>
import axios from 'axios';
export default {
	name: 'Hook',
	data() {
		return {
			posts: []
		};
	},
	methods: {},
	created() {
		axios
			.get('https://jsonplaceholder.typicode.com/posts')
			.then(response => {
				//console.log(response);
				this.posts = response.data;
			})
			.catch(error => {
				console.log(error);
			});
	}
};
</script>

<style>
h1 {
	color: gray;
	text-align: center;
}
</style>
