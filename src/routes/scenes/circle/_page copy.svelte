<script>

    import { fade } from "svelte/transition";
    import { seconds } from "$lib/clock";
    import { user } from "$lib/realtime";

    let animating = false;
    let alternated = $user.num % 2 === 0;

    function switchTarget( s ){
        if( s % 3 === 0 ){
            animating = true;
        }
    }

    $: switchTarget( $seconds );

</script>

<div transition:fade>
    <main class:animating class:alternated></main>
</div>

<style>

    main {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100%;
    }
    main.animating {
        animation: slide 2s linear;
        animation-iteration-count: infinite;
        background: linear-gradient(90deg, rgba(0,0,0,1) 0%, rgba(255,255,255,1) 100%);
    }
    main.animating.alternated {
        animation-delay: 1s;
    }

    @keyframes slide {
        from {
            transform: translateX(-100vw);
        }
        to {
            transform: translateX(100vw);
        }
    }

</style>