<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">

	import Counter from '$lib/Counter.svelte';
	import { DirectSecp256k1HdWallet } from "@cosmjs/proto-signing";
	import { assertIsBroadcastTxSuccess, SigningStargateClient, StargateClient } from "@cosmjs/stargate";

	const mnemonic = "surround miss nominee dream gap cross assault thank captain prosper drop duty group candy wealth weather scale put";
	const wallet = await DirectSecp256k1HdWallet.fromMnemonic(mnemonic);
	const [firstAccount] = await wallet.getAccounts();
	console.log("account: "+firstAccount.address);


</script>


<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<div class="welcome">
			<picture>
				<source srcset="svelte-welcome.webp" type="image/webp" />
				<img src="svelte-welcome.png" alt="Welcome" />
			</picture>
		</div>
	</h1>

	<div class="card border-secondary border">
		<div class="card-body">
			<h5 class="card-title">Special title treatment</h5>
			<p class="card-text">With supporting text below as a natural lead-in to
				additional content.</p>
			<a href="javascript: void(0);" class="btn btn-secondary btn-sm">Button</a>
		</div> <!-- end card-body-->
	</div>

	<h2>Utribe Wallet Cosmos MVP
	</h2>

	<Counter />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
