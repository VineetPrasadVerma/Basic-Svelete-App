<script>

    import PollDetails from './PollDetails.svelte'
    import PollsStore from '../stores/PollsStore.js'

    export let polls = []

    PollsStore.subscribe(data => {
        polls = data
    })
    
</script>

<div class="poll-list">
    {#each polls as poll (poll.id)}
        <PollDetails {poll} on:vote/>
    {/each}
</div>

<style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }
</style>