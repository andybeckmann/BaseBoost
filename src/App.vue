<template>
	<div id="app">
		<div class="app--demo">
			<h1>BaseBoost</h1>
			<form @submit.prevent="sendForm">
				<BaseInput
					v-model="data.title"
					label="Text"
					type="text"
				/>
				<BaseSelect
					v-model="data.subject"
					label="Select"
					:options="['Option A', 'Option B', 'Option C']"
				/>
				<BaseRadioGroup
					v-model="data.preference"
					label="Radio"
					:options="[{ label: 'Option A', value: 'Option A' }, { label: 'Option B', value: 'Option B'}, { label: 'Option C', value: 'Option C'}]"
				/>
				<div class="checkbox-group">
					<label>Checkbox</label>
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
				<BaseButton
					type="submit"
					value="Submit"
				/>
			</form>
		</div>
		<div class="app--data">
			<div><span>{</span></div>
			<div>&nbsp;&nbsp;<span>data:</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;<span>{</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>title:</span> <b>{{ data.title }}</b><span>,</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>subject:</span> <b>{{ data.subject }}</b><span>,</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>preference:</span> <b>{{ data.preference }}</b><span>,</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionA:</span> <b>{{ data.optionA }}</b><span>,</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionB:</span> <b>{{ data.optionB }}</b><span>,</span></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span>optionC:</span> <b>{{ data.optionC }}</b></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;<span>}</span></div>
			<div><span>}</span></div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			data: {
				title: '',
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

#app {
	display: flex;
	width: 100%;

	.app--demo, .app--data {
		width: 50%;
		padding: 50px;
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
		border-radius: 10px;
		background: #eee;
		color: #111;
		font-size: 20px;
		margin: 50px 50px 50px 0;

		span {
			color: #999;
		}
	}
}
</style>
