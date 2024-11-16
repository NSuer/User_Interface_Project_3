<script>
    let uploadedImage = null;

    function fileUpload(event) {
        const file = event.target.files[0];

        if (file) {
            const reader = new FileReader();
            reader.onload = () => {
                uploadedImage = reader.result;
            };

            reader.readAsDataURL(file);
        }
    }

    function resetUpload() {
        uploadedImage = null;
    }

    import { onMount } from "svelte";
    let leds = []; // stores LED positions and effects

    const handleDragStart = (event, color) => {
      event.dataTransfer.setData('effect', color);
    }

    const handleDrop = (event) => {
      event.preventDefault();

      const effect = event.dataTransfer.getData('effect');
      const x = event.clientX - event.target.offsetLeft;
      const y = event.clientY - event.target.offsetTop;

      leds = [...leds, {x, y, effect }];
    };

    const handleDragOver = (event) => {
      event.preventDefault();
    }

</script>

<div class="blinky-builder">
    <h1>Blinky Builder</h1>
    <div class="upload-section">
      <label for="upload">Upload Your Artwork: </label>
      <input type="file" id="upload" accept="image/*" on:change={fileUpload} />
    </div>
  
    {#if uploadedImage}
      <div 
        id="image-container" 
        on:drop={handleDrop} 
        on:dragover={handleDragOver} 
        class="uploaded-image"
        role="region"
        aria-label="LED drop area">
        <img id="uploaded-image" src={uploadedImage} alt="Uploaded Artwork" />
      </div>
    {/if}

    <!-- LEDs will be dynamically rendered here -->
    {#each leds as led}
      <div 
        style="left: {led.x}px; top: {led.y}px;" 
        class={led.effect} 
        role="button" 
        aria-label={`LED with ${led.effect} effect`}>
      </div>
    {/each}

    <div class="leds">
      <!-- Placeholder LEDs -->
      {#each ["red", "orange", "yellow", "green", "blue", "purple", "pink", "white"] as color}
        <img src={`https://via.placeholder.com/50/${color}?text=+`} alt="{color} LED" draggable="true" on:dragstart={(e) => handleDragStart(e, color)}/>
      {/each}
    </div>
    
    <div class="buttons">
      <button draggable="true" on:dragstart={(e) => handleDragStart(e, 'flash')}>Make it Flash</button>
      <button draggable="true" on:dragstart={(e) => handleDragStart(e, 'fade')}>Make it Fade</button>
      <button on:click={resetUpload}>Reset</button>
    </div>

</div>



<style>
    .blinky-builder {
      text-align: center;
      font-family: Arial, sans-serif;
      margin: 20px;
    }
  
    .upload-section {
      margin: 20px 0;
    }
  
    .leds {
      display: flex;
      justify-content: center;
      gap: 10px;
      margin: 20px 0;
    }
  
    .leds img {
      width: 50px;
      cursor: pointer;
    }
  
    .uploaded-image {
      margin-top: 20px;
      max-width: 100%;
      border: 1px dashed #ccc;
      padding: 10px;
      background-color: #f8f8f8;
    }
  
    .buttons {
      margin-top: 20px;
    }
  
    .buttons button {
      background-color: #ff00ff;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      margin: 0 10px;
      cursor: pointer;
      font-size: 16px;
    }
  
    .buttons button:hover {
      background-color: #d400d4;
    }
  
    .reset-button {
      background-color: #333;
    }
  
    .reset-button:hover {
      background-color: #555;
    }

    #led-toolbox {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
  }

  .led {
    width: 60px;
    height: 20px;
    background-color: red;
    color: white;
    text-align: center;
    line-height: 20px;
    border-radius: 5px;
    cursor: grab;
  }

  .dropped {
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: red;
    border-radius: 50%;
    cursor: grab;
  }

  #image-container {
    position: relative;
    width: 800px; /* Set your desired width */
    height: 500px; /* Set your desired height */
    border: 1px solid black;
    overflow: hidden;
  }

  #background-image {
    width: 100%;
    height: 100%;
  }

  @keyframes fade {
    0%, 100% {
      opacity: 1;
    }
    50% {
      opacity: 0.3;
    }
  }

  @keyframes flash {
    0%, 100% {
      opacity: 1;
    }
    50% {
      opacity: 0;
    }
  }

  .fade {
    animation: fade 2s infinite;
  }

  .flash {
    animation: flash 1s infinite;
  }
  </style>