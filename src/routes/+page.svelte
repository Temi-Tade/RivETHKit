<script lang="ts">
	import About from "../ui/About.svelte";
	import Header from "../ui/Header.svelte";
	import SetUp from "../ui/SetUp.svelte";
	import ToTopButton from "../ui/ToTopButton.svelte";
    import { browser } from "$app/environment";

    let showScrollToTopButton: boolean = $state(false);

    if (browser) {
        window.onscroll = function() {
            if (window.scrollY > 100) {
                showScrollToTopButton = true;
            } else { 
                showScrollToTopButton = false;
            }
        }
    }
    

</script>

<div>
    <Header/>
    <About/>
    <SetUp/>
    {#if showScrollToTopButton} 
        <ToTopButton/>
    {/if}
</div>

<!-- nav -->