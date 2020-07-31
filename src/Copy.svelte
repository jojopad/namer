<script>
    import { NotificationDisplay, notifier } from '@beyonk/svelte-notifications'

    export let value = '';

    function copy() {
        navigator.clipboard.writeText(value);
        notifier.info(`Copied!`);
    }
</script>

<NotificationDisplay />

<button
        style="margin-right: 5px"
        title="Copy to clipboard"
        on:click={copy}>
    <span class="jam jam-clipboard"></span>
</button>