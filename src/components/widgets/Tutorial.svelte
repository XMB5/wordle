<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the <strong>TRICKORDLE</strong> in {ROWS} tries.</div>
<div>
	One trick tile will be randomly changed in every row. 
</div>
<div class:complete={visible} class="examples">
	<div><strong>Example (word: house)</strong></div>
	<div class="row">
		<Tile value="h" state="🟩" />
		<Tile value="o" state="⬛" />
		<Tile value="t" state="⬛" />
		<Tile value="e" state="⬛" />
		<Tile value="l" state="⬛" />
	</div>
	<div>The letter <strong>O</strong> is in the correct spot, but it is grayed out because it is a trick</div>
	<div class="row">
		<Tile value="p" state="⬛" />
		<Tile value="a" state="⬛" />
		<Tile value="r" state="⬛" />
		<Tile value="k" state="🟨" />
		<Tile value="a" state="⬛" />
	</div>
	<div>The letter <strong>K</strong> is not not in the word, but it is yellow because it is a trick</div>
	<div class="row">
		<Tile value="g" state="⬛" />
		<Tile value="l" state="🟩" />
		<Tile value="a" state="⬛" />
		<Tile value="z" state="⬛" />
		<Tile value="e" state="🟩" />
	</div>
	<div>The letter <strong>L</strong> is not in in the word, but it is green because it is a trick</div>
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
