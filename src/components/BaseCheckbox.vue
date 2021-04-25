<template>
	<div class="input-group">
		<input
			type="checkbox"
			:checked="modelValue"
			@change="$emit('update:modelValue', $event.target.checked)"
		/>
		<label v-if="label">{{ label }}</label>
	</div>
</template>

<script>
export default {
	props: {
		label: {
			type: String,
			default: ''
		},

		modelValue: {
			type: Boolean,
			default: false
		}
	}
}
</script>

<style lang="scss" scoped>
.input-group {
	padding: 0 0 15px 0;
	position: relative;
	border-top: 1px solid #ddd;
	display: block;
	padding-top: 15px;

	label {
		font-size: 18px;
	}

	input[type=checkbox] {
		position: absolute;
		opacity: 0; 
		z-index: 2;
		cursor: pointer;
		font-size: 18px;
		top: -1px;
		left: 1px;
		width: 26px;
		height: 26px;

		& + label {
			position: relative;
			cursor: pointer;
			padding: 0;
			margin-right: 15px;
		}

		& + label:before {
			content: '';
			margin-right: 10px;
			margin-top: -2px;
			display: inline-block;
			vertical-align: text-top;
			width: 26px;
			height: 26px;
			border: 1px solid #ccc;
			background: #fff;
			border-radius: 3px;
		}

		&:hover + label:before {
			background: #eee;
		}

		&:checked + label:before {
			background: #111;
		}

		&:checked + label:after {
			content: '\000D7';
			color: #fff;
			position: absolute;
			left: 8px;
			top: -2px;
			font-size: 20px;
			font-weight: bold;
			z-index: 1;
		}
	}
}
</style>