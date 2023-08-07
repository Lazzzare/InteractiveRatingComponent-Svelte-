<script lang="ts">

    import ResultImage from '../assets/Result.svg'

    export let rating: number;
    export let title: string;
    export let content: string;

</script>

<div class="flex flex-col justify-center items-center gap-y-6 md:gap-y-8">
    <img
    src={ResultImage}
    alt="ResultImage"
    class="w-[149px] h-[96px] md:w-[162px] md:h-[108px]"
  />
  <p class="bg-DarkBlue text-Orange px-3 md:px-[19px] py-[5px] md:py-[4px] leading-6 text-sm md:text-[15px] rounded-[22.5px] items-center text-center">
    You selected {rating} out of 5
  </p>
</div>

<div class="items-center flex flex-col gap-y-[10px] md:gap-y-[7px] mt-6 md:mt-8">
    <h1 class="text-White text-2xl md:text-[28px] font-bold">
      {title}
    </h1>
    <p class="text-LightGray leading-[22px] text-sm md:text-[15px] md:leading-[24px] text-center">
      {content}
    </p>
  </div>