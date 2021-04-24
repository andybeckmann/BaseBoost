<template>
	<div id="app">
		<h1>{{ item.title }}</h1>
		<form>
			<BaseInput
				v-model="item.title"
				label="Title"
				type="text"

			/>
			<BaseButton
				type="submit"
				value="Submit"
			/>
		</form>
	</div>
</template>

<script>
import BaseInput from './components/BaseInput'
import BaseButton from './components/BaseButton'

export default {
	data () {
		return {
			item: {
				title: 'x'
			}
			
		}
	},

	components: {
		BaseButton, BaseInput
	}
}
</script>

<style>
* {
	box-sizing: border-box;
	font-family: sans-serif;
}
</style>
