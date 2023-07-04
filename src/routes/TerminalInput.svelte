<script lang="ts">
    import { onMount } from "svelte";

    let terminalInput:HTMLSpanElement = null;

    onMount(() => {
        terminalInput.focus();
    })

</script>


<span class="text-lime-400 font-mono rounded-none outline-none" bind:this={terminalInput} contenteditable="true" data-path="maya@bbb > " ></span>

<style>
    span::before {
        content: attr(data-path);
    }
    span::after {
        content: ".";
        background-color: lime;
        animation: blink infinite linear 1s;
    }

    @keyframes blink {
        from {opacity: 1;}
        to {opacity: 0;}
    }
    </style>