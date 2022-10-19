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
		auth: false,
		nakama: [],
	}),
	mounted() {
		this.$nextTick().then(() => {
			this.auth = true
			console.log('nextTick')
			console.log(this.$refs['elem'])
		})
	},
	methods: {
		async update() {
			this.nakama = ['neko', 'inu', 'ookami', 'hebi']
		},
	},
	watch: {
		auth(auth) {
			if (auth) {
				this.update()
			}
		},
	},
}
</script>
