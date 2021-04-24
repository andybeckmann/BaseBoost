<template>
	<button class="button">
		{{ value }}
	</button>
</template>

<script>
export default {
	props: {
		value: String
	}
}
</script>

<style>
.button {
	background: #111;
	color: #fff;
	border: none;
	border-radius: 4px;
	font-size: 18px;
	font-weight: bold;
	cursor: pointer;
	padding: 15px 20px;
}
</style>
