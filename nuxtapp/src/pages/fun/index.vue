<template>
	<div>
		<div>
			<ul id="nakama">
				<li v-for="(n, index) in nakama" :key="index" ref="elem" class="animal">{{ n }}</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Fun',
	data: () => ({
		nakama: ['neko', 'inu', 'ookami', 'hebi'],
	}),
	mounted() {
		this.$nextTick().then(() => {
			console.log('nextTick')
			console.log(this.$refs['elem'])
		})
	},
}
</script>
