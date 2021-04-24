<template>
	<div id="app">
		<div class="app--demo">
			<h1>BaseBoost</h1>
			<form>
				<BaseInput
					v-model="data.title"
					label="Title"
					type="text"
				/>
				<BaseSelect
					v-model="data.subject"
					label="Subject"
					:options="['Option A', 'Option B', 'Option C']"
				/>
				<BaseCheckbox
					v-model="data.subscribe"
					label="Subscribe to newsletter"
				/>
				<BaseButton
					type="submit"
					value="Submit"
				/>
			</form>
		</div>
		<div class="app--data">
			<div>{</div>
			<div>&nbsp;&nbsp;data:</div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;{</div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;title: <b>{{ data.title }}</b>,</div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;subject: <b>{{ data.subject }}</b>,</div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;subscribe: <b>{{ data.subscribe }}</b></div>
			<div>&nbsp;&nbsp;&nbsp;&nbsp;}</div>
			<div>}</div>
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
				subscribe: false
			}
			
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
		
	}

	.app--data {
		border: 5px dashed #ccc;
		border-radius: 10px;
		background: #eee;
		font-size: 20px;
		margin: 50px 50px 50px 0;
	}
}
</style>
