<script>
    
    import ControlButton from "$lib/ControlButton.svelte";

</script>

<nav>
    <ControlButton id={4}>Update</ControlButton>
</nav>

<style>

    nav {
        padding: 1rem;
        width: 100vw;
        height: var(--100vh);
        display: flex;
        position: fixed;
        left: 0;
        top: 0;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        font-size: 6rem;
    }

    nav :global( button ){
        margin: 0.3rem;
    }
    
    @media (orientation: portrait){
        nav :global( button ){
            transform: rotate(-90deg);
        }
    }

</style>