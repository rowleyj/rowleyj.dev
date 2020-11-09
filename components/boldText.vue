<template>
	<span style="font-weight: bold"> {{text}} </span>
</template>

<script>
export default {
	props: {
		text: {
			type: String,
			default: null
		}
	}
}
</script>