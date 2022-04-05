<script>
	export let name;
	export let counter = 0;
	export let counter2 = 1;

	export function countUp(){
		counter++;
	}

	export function countUp2(){
		counter2++;
	}

	// totalはconterとcounter2に依存している。
	// どちらかが変更されるとリアクティブに変更される。
	$: total = counter + counter2;

	export function renameTitle(){
		document.title = "hoge";
	}
</script>

<main>
	<span>
		<p>counter: {counter}</p>
		<p>counter2: {counter2}</p>
		<p>total: {total}</p>
		<button on:click={countUp}>countUp_定義済みのfunciton呼び出し</button><br>
		<button on:click={() => counter++}>その場で定義してあるカウントアップ</button><br>
		<button on:click={countUp2}>countUp2_引数有りfunciton呼び出し</button><br>
	</span>

	<button on:click={renameTitle}>title変更</button>
	<br><br>

	<span>
		
	</span>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>