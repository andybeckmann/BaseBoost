<template>
	<div id="app">
		<div class="app--demo">
			<h1>BaseBoost</h1>
			<form @submit.prevent="sendForm">
				<fieldset>
					<legend>Text input example</legend>
					<p>What is your name?</p>
					<BaseInput
						v-model="data.name"
						label="Text"
						type="text"
					/>
				</fieldset>
				<fieldset>
					<legend>Select options example</legend>
					<p>Do you prefer Option A, Option B, or Option C?</p>
					<BaseSelect
						v-model="data.subject"
						label="Select"
						:options="['Option A', 'Option B', 'Option C']"
					/>
				</fieldset>
				<fieldset>
					<legend>Radio group example</legend>
					<p>Do you prefer Option A, Option B, or Option C?</p>
					<BaseRadioGroup
						v-model="data.preference"
						label=""
						:options="[{ label: 'Option A', value: 'Option A' }, { label: 'Option B', value: 'Option B'}, { label: 'Option C', value: 'Option C'}]"
					/>
				</fieldset>
				<fieldset>
					<legend>Checkbox group example</legend>
					<p>Do you prefer Option A, Option B, or Option C?</p>
					<div class="checkbox-group">
						<BaseCheckbox
							v-model="data.optionA"
							label="Option A"
						/>
						<BaseCheckbox
							v-model="data.optionB"
							label="Option B"
						/>
						<BaseCheckbox
							v-model="data.optionC"
							label="Option C"
						/>
					</div>
				</fieldset>
				<BaseButton
					type="submit"
					value="Submit"
				/>
			</form>
		</div>
		<div class="app--data">
			<div>
				<div><span>{</span></div>
				<div>&nbsp;&nbsp;<span>data:</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;<span>{</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>name:</span> <b>{{ data.name }}</b><span>,</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>subject:</span> <b>{{ data.subject }}</b><span>,</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>preference:</span> <b>{{ data.preference }}</b><span>,</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionA:</span> <b>{{ data.optionA }}</b><span>,</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionB:</span> <b>{{ data.optionB }}</b><span>,</span></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionC:</span> <b>{{ data.optionC }}</b></div>
				<div>&nbsp;&nbsp;&nbsp;&nbsp;<span>}</span></div>
				<div><span>}</span></div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			data: {
				name: '',
				subject: '',
				preference: '',
				optionA: false,
				optionB: false,
				optionC: false
			}
			
		}
	},

	methods: {
		sendForm () {
			// XHR to API here
		}
	}
}
</script>

<style lang="scss">
* {
	box-sizing: border-box;
	font-family: sans-serif;
}

body {
	padding: 0;
	margin: 0;
}

form {
	fieldset {
		border: 1px solid #ddd;
		margin: 25px 0;
		border-radius: 4px;

		legend {
			font-weight: bold;
			font-size: 14px;
			text-transform: uppercase;
		}
	}
}

#app {
	display: flex;
	width: 100%;

	.app--demo, .app--data {
		width: 50%;
		padding: 15px 50px;
	}

	.app--demo {
		.checkbox-group {
			padding: 0 0 15px 0;
			position: relative;

			& > label {
				text-transform: uppercase;
				font-size: 14px;
				font-weight: bold;
				margin-bottom: 10px;
				display: inline-block;
			}
		}
	}

	.app--data {
		padding: 50px 50px 50px 0;

		> div {
			background: #eee;
			padding: 50px;
			border-radius: 4px;
			color: #111;
			font-size: 20px;
		}

		span {
			color: #999;
		}
	}
}
</style>
