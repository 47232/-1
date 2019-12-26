<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/* @import "common/reset.css"; */
	*{ margin:0; padding: 0;}
	html,body{
		width: 100%;
		height: 100%;
	}
	#app{
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
	}
</style>
