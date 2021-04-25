<template>
	<div class="input-group">
		<label v-if="label">{{ label }}</label>
		<input
			v-bind="$attrs"
			:placeholder="label"
			:value="modelValue"
			@input="$emit('update:modelValue', $event.target.value)"
		>
	</div>
</template>

<script>
export default {
	props: {
		label:  {
			type: String,
			default: ''
		},

		modelValue: {
			type: [String, Number],
			default: ''
		}
	}
}
</script>

<style lang="scss" scoped>
.input-group {
	padding: 0 0 15px 0;
	position: relative;
}

label {
	text-transform: uppercase;
	font-size: 14px;
	font-weight: bold;
	display: inline-block;
	margin-top: 10px;
	margin-bottom: 10px;
}

input{
	background: #fff;
	padding: 15px 20px;
	margin: 0 0 10px;
	outline: none;
	border: 1px solid #ccc;
	font-size: 18px;
	width: 100%;
	border-radius: 4px;
	display: block;
	box-shadow: 	
				0 3px 3px rgba(0, 0, 0, 0.05),
				inset 0px 10px 10px #eee;
}
</style>