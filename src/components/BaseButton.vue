<template>
	<div class="input-group">
		<button v-bind="$attrs" class="button">
		{{ value }}
		</button>
	</div>
</template>

<script>
export default {
	props: {
		value: String
	}
}
</script>

<style lang="scss" scoped>
.input-group {
	padding: 0 0 15px 0;

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
}
</style>
