<template>
	<div class="input-group">
		<input 
			type="radio"
			:id="uuid"
			:checked="modelValue === value"
			:value="value"
			@change="$emit('update:modelValue', value)"
			v-bind="$attrs"
		/>
		<label v-if="label" :for="uuid">{{ label }}</label>
	</div>
</template>

<script>
import UniqueID from '../features/UniqueID'
export default {
	props: {
		label: {
			type: String,
			default: ''
		},

		modelValue: {
			type: [String, Number],
			default: ''
		},

		value: {
			type: [String, Number],
			required: true
		}
	},

	setup () { 
		const uuid = UniqueID().getID() 
		return { 
			uuid 
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
}

input[type=radio] {
	position: absolute;
	opacity: 0;
	z-index: 2;
	width: 26px;
    height: 26px;
    top: -1px;
    left: 1px;
    margin: 0; 
    cursor: pointer;
    font-size: 18px;
	
	& + label {
		position: relative;
		cursor: pointer;
		padding: 0;
		margin-right: 15px;
		margin-top: 15px;
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
		border-radius: 50%;
	}

	&:hover + label:before {
		background: #eee;
	}

	&:checked + label:before {
		background: #111;
		border-radius: 50%;
	}

	&:checked + label:after {
		content: '';
		width: 26px;
		height: 26px;
		border: 1px solid #ccc;
		background: #fff;
		border-radius: 50%;
		transform: scale(.35);
		position: absolute;
		top: -2px;
		left: 0;
		z-index: 1;
	}
}
</style>