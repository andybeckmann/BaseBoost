<template>
	<div class="input-group">
		<label v-if="label">{{ label }}</label>
		<select 
			:value="modelValue"
			:placeholder="label"
			v-bind="{
				...$attrs,
				onChange: ($event) => { $emit('update:modelValue', $event.target.value) }
			}"
		>
			<option
				v-for="option in options"
				:value="option"
				:key="option"
				:select="option === modelValue"
			>
			{{ option }}
			</option>
			
		</select>
	</div>
</template>

<script>
export default {
	props: {
		label:  {
			type: String,
			default: ''
		},

		options: {
			type: Array,
			required: true
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

	label {
		text-transform: uppercase;
		font-size: 14px;
		font-weight: bold;
		margin-bottom: 5px;
		display: inline-block;
	}

	select {
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
}
</style>