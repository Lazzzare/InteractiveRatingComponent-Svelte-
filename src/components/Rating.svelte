<script lang="ts">
	import Result from './Result.svelte';
    import Star from '../assets/Star.svg'

    export let title: string;
    export let content: string;

    let rating = 0
    let result = false;

    const resultClick = (showResult) => {
        result = !showResult
    }

    const handleClick = (selectedRating) => {
        rating = selectedRating
    }
</script>



<div class="box px-6 md:px-8 pt-6 md:pt-8 py-8 w-[327px] md:w-[412px] rounded-[15px]">
    {#if result === false}
    <img src={Star} alt="StarIcon" class="p-4 bg-DarkBlue rounded-full w-12 h-12">
    <div class="mt-4 md:mt-[30px] flex flex-col gap-y-[10px] md:gap-y-3">
        <h1 class="text-2xl md:text-[28px] font-bold text-White">{title}</h1>
        <p class="text-LightGray text-sm md:text-[15px] md:w-[340px] leading-6">{content}</p>
    </div>
    <div class="w-full items-center flex flex-row gap-x-[18px] mt-6">
        {#each [1,2,3,4,5] as item}
        <button on:click={() => handleClick(item)} class={`w-[42px] md:w-[51px] md:h-[51px] h-[42px] text-sm md:text-base md:font-bold leading-6 tracking-[0.175px] md:tracking-[0.2px]
            bg-DarkBlue rounded-full items-center text-MediumGray duration-300 hover:bg-MediumGray hover:text-White ${rating === item ? "bg-Orange text-[#fff]" : null}`}>{item}</button>
        {/each}
    </div>
    <button on:click={() => resultClick(result)} class="uppercase mt-6 w-full bg-Orange text-White py-3 px-[109px] rounded-[22.5px] duration-300 hover:bg-White hover:text-Orange">Submit</button>
    {:else}
    <Result rating={rating} title="Thank You" content="We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch!"/>
    {/if}
</div>
