<template>
	<v-app>
		<v-app-bar
			fixed
			app
		>
			<v-toolbar-title style="font-family: Impact, sans-serif;">rowleyj.dev</v-toolbar-title>
		</v-app-bar>
		<v-main>
			<v-container>
				<nuxt />
			</v-container>
		</v-main>
		<v-footer
			:absolute="!fixed"
			app
		>
			<span>&copy; {{ new Date().getFullYear() }}</span>
		</v-footer>
	</v-app>
</template>

<script>
export default {
	data () {
		return {
			fixed: false,
		}
	}
}
</script>
