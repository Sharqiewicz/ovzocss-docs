<script>
	import logo from '$lib/assets/logo.svg';
	import 'ovzocss';
</script>

<nav class='nav flex align-center background-white'>
	<a href='/' class='link-primary mx-3'><img src={logo} alt='ovzocss logo' width={40}/></a>
	<a href='/' class='link-primary mx-3'>OvzoCSS</a>
	<a href='/docs' class='link-primary mx-3'>Docs</a>
</nav>
<slot />


<style>
	.nav{
		position: sticky;
		top: 0;
		left:0;
		right:0;
		box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.1);
		z-index: 200;
		padding: 0.5rem 1rem;
	}
</style>