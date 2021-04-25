<template>
	<div class="input-group">
		<label v-if="label">{{ label }}</label>
		<div class="select-item-wrapper">
			<select 
				:value="modelValue"
				:placeholder="label"
				v-bind="{
					...$attrs,
					onChange: ($event) => { $emit('update:modelValue', $event.target.value) }
				}"
			>
				<option disabled selected>Choose an option...</option>
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
	position: relative;

	label {
		text-transform: uppercase;
		font-size: 14px;
		font-weight: bold;
		margin-bottom: 10px;
		display: inline-block;
	}

	select {
		background: #111;
		color: #fff;
		width: 175px;
		padding: 16px;
		display: inline-block;
		margin: 0;
		border-radius: 3px;
		-webkit-appearance: none;
		border: none;
		position: relative;
		min-width: 100%;
		font-size: 18px;
	}

	.select-item-wrapper {
		display: block;
		position: relative;
	}

	.select-item-wrapper::after {
		content: '\25BE';
		right: 21px;
		top: 10px;
		position: absolute;
		color: #fff;
		font-size: 24px;
	}
}
</style>