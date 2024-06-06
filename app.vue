<template>
	<div>
		<h1>{{ message }}</h1>
	</div>
</template>
<script setup lang="ts">
import axios from 'axios'
const message = ref('')

const restAPI = async () => {
	try {
		const response = await axios.get('http://localhost:3000/api/hello')
		message.value = response.data
	} catch (error) {
		console.log('error: ', error)
	}
}
onMounted(restAPI)
</script>
