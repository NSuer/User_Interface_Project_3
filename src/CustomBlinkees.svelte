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

</script>

<div class="blinky-builder">
    <h1>Blinky Builder</h1>
    <div class="upload-section">
        <label for="upload">Upload Your Artwork: </label>
        <input type="file" id="upload" accept="image/*" on:change={fileUpload} />
    </div>

    {#if uploadedImage}
        <div class="uploaded-image">
            <img src={uploadedImage} alt="Uploaded Artwork" />
        </div>
    {/if}

    <div class="leds">
        <!-- Placeholder LEDs -->
        {#each ["red", "orange", "yellow", "green", "blue", "purple", "pink", "white"] as color}
            <img src={`https://via.placeholder.com/50/${color}?text=+`} alt="{color} LED" />
        {/each}
    </div>
    
    <div class="buttons">
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
  </style>