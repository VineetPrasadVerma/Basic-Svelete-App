<script>
    let showModal = true
    let isPromo = true;
</script>

{#if showModal}
    <div class='backdrop' class:promo={isPromo}>
        <div class="modal">
            <p>Signup for offers.</p>
        </div>
    </div>
{/if}

<style>
    .backdrop{
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0,0.8);
    }

    .modal{
        padding: 10px;
        border-radius: 10px;
        background: white;
        text-align: center;
        max-width: 400px;
        margin: 5% auto;
    }

    .promo .modal{
        background: crimson;
        color: white;
    }

</style>