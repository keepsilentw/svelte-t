<script lang="ts">
	export let segment: string;
</script>

<style>
	nav {
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">home</a></li>
		<li>
			<a rel=prefetch aria-current="{segment === 'nested' ? 'page' : undefined}" href="nested">nested</a>
		</li>
		<li>
			<a rel=prefetch aria-current="{segment === 'reactive' ? 'page' : undefined}" href="reactive">reactive</a>
		</li>
		<li>
			<a rel=prefetch aria-current="{segment === 'props' ? 'page' : undefined}" href="props">props</a>
		</li>
		<li>
			<a rel=prefetch aria-current="{segment === 'logic' ? 'page' : undefined}" href="logic">logic</a>
		</li>
		<li>
			<a rel=prefetch aria-current="{segment === 'events' ? 'page' : undefined}" href="events">events</a>
		</li>
		<li>
			<a rel=prefetch aria-current="{segment === 'bindings' ? 'page' : undefined}" href="bindings">bindings</a>
		</li>
	</ul>
</nav>
