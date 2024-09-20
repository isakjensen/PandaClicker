<script lang="ts">

    let points = 0;

    function addPoints() {
        points += 1;
    }

</script>

<main class="flex h-screen w-screen flex-row">
    <div class="relative flex h-full w-2/3 click-bg" style="background-image: url(https://i.imgur.com/e1kDRCK.png)">

        <div class="absolute top-32 left-1/2 transform -translate-x-1/2">
            <h1 class="text-[#FFF0D1] text-6xl text-center font-rubik">{points}</h1>
        </div>

        <span class="absolute top-64 left-1/2 transofmr -translate-x-1/2 text-[#FFEB55] text-3xl font-rubik select-none">+ 1</span>

        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
            <button on:click={addPoints}>
                <img src="https://i.imgur.com/8LW3QsM.png" alt="" class="w-64 h-64 hover-scale z-50">
            </button>
        </div>
    </div>
  
    <div class="flex h-full w-1/3 bg-[#3B3030]">
  
      <div class="flex flex-col gap-2 w-full mt-16">
        <h1 class="text-[#8FD14F] text-6xl text-center font-rubik">Panda Clicker</h1>
        <span class="text-3xl text-[#FFF0D1] text-center font-amsterdam">Collect Panda Points and upgrade your jungle</span>
      </div>
  
    </div>
</main>
  