<script>
    export let tooltip = false // prevent blank tooltips
    let width=tooltip.length < 50 ? "100%":100+tooltip.length+"%";
</script>

<button data-tooltip={tooltip} style="--width:{width}">
	<slot></slot>
</button>

<style>
    button {
        background:transparent;
        border:none;
        font-size: inherit;
        border-bottom: 1px dotted hotpink;
    }
    [data-tooltip]:before {
        width: var(--width);
    }
</style>