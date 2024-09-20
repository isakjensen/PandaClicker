<script lang="ts">
    	import { scale } from 'svelte/transition';
        import { quintOut } from 'svelte/easing';

    let points = 0;
    let pointsList: any = [];

    function addPoints(event: any) {
        points += 1;

        let randomPosition = Math.floor(Math.random() * 4);

        pointsList[randomPosition] = true

        setTimeout(() => {
            pointsList[randomPosition] = false
        }, 500);
    }

</script>

<main class="flex h-screen w-screen flex-row">
    <div class="relative flex h-full w-2/3 click-bg" style="background-image: url(https://i.imgur.com/e1kDRCK.png)">

        <div class="absolute top-32 left-1/2 transform -translate-x-1/2">
            <h1 class="text-[#FFF0D1] text-6xl text-center font-rubik">{points}</h1>
        </div>

        {#if pointsList[0] === true}
            <span
                class="absolute top-64 left-[30rem] text-[#FFEB55] text-3xl font-rubik select-none rotate-12"
                transition:scale={{ duration: 250, delay: 0, opacity: 0.5, start: 0.5, easing: quintOut }}
            >+ 1</span>
        {/if}
        {#if pointsList[1] === true}
            <span
                class="absolute top-60 left-[35rem] text-[#FFEB55] text-3xl font-rubik select-none -rotate-12"
                transition:scale={{ duration: 250, delay: 0, opacity: 0.5, start: 0.5, easing: quintOut }}
            >+ 1</span>
        {/if}
        {#if pointsList[2] === true}
            <span 
                class="absolute top-72 left-[35rem] text-[#FFEB55] text-3xl font-rubik select-none -rotate-6"
                transition:scale={{ duration: 250, delay: 0, opacity: 0.5, start: 0.5, easing: quintOut }}
            >+ 1</span>
        {/if}
        {#if pointsList[3] === true}
            <span 
                class="absolute top-64 left-[40rem] text-[#FFEB55] text-3xl font-rubik select-none -rotate-12"
                transition:scale={{ duration: 250, delay: 0, opacity: 0.5, start: 0.5, easing: quintOut }}
            >+ 1</span>
        {/if}

        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
            <button on:click={addPoints}>
                <img src="https://i.imgur.com/8LW3QsM.png" alt="" class="w-64 h-64 hover-scale z-50">
            </button>
        </div>
    </div>
  
    <div class="flex flex-col h-full w-1/3 bg-[#3B3030] px-8 gap-12">
  
      <div class="flex flex-col gap-2 w-full mt-16">
        <h1 class="text-[#8FD14F] text-6xl text-center font-rubik">Panda Clicker</h1>
        <span class="text-3xl text-[#FFF0D1] text-center font-amsterdam">Collect Panda Points and upgrade your jungle</span>
      </div>

      <div class="w-full flex flex-col gap-4 bg-[#86D293] p-4 rounded-lg">
        <h1 class="text-4xl font-rubik text-[#3B3030]">Pandaclicker - 50 P$</h1>
        <span class="text-black">Buy this upgrade and gain more coins!</span>
      </div>
  
    </div>
</main>
  