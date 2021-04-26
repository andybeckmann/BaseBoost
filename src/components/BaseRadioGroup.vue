<template>
	<div class="radio-group">
		<BaseRadio
			v-for="option in options"
			:key="option.value"
			:label="option.label"
			:value="option.value"
			:name="name"
			:modelValue="modelValue"
			@update:modelValue="$emit('update:modelValue', $event)"
		/>
	</div>
</template>

<script>
export default {
	props: {
		label: {
			type: String,
			default: ''
		},

		options: {
			type: Array,
			required: true
		},

		name: {
			type: String,
			required: true
		},

		modelValue: {
			type: [String, Number],
			required: true
		}
	}
}
</script>

<style lang="scss" scoped>
.radio-group {
	padding: 0 0 15px 0;
	position: relative;

	label {
		text-transform: uppercase;
		font-size: 14px;
		font-weight: bold;
		margin-bottom: 10px;
		display: inline-block;
	}
}
</style>