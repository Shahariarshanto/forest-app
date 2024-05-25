
<script>
  // Declare variables for length, height, and volumes
  let lengthInches = 0;
  let heightInches = 0;
  let volumeCubicFeet = 0;
  let volumeCubicMeter = 0;

  // Function to calculate volume based on input values
  function calculateVolume() {
    // Convert inches to feet
    const lengthFeet = lengthInches / 12;
    const heightFeet = heightInches / 12;

    // Calculate volume in cubic feet
    volumeCubicFeet = lengthFeet * lengthFeet * heightFeet;

    // Convert cubic feet to cubic meters
    volumeCubicMeter = volumeCubicFeet * 0.0283168;
  }

  // Function to reset input values and calculated volumes
  function clearValues() {
    lengthInches = 0;
    heightInches = 0;
    volumeCubicFeet = 0;
    volumeCubicMeter = 0;
  }
</script>

<div class="container md:sm mx-auto  max-w-md mt-16">

  <div class="flex flex-col w-full px-6">
    <!-- Display volume in cubic feet -->
    <div class="grid h-20 card bg-base-300 rounded-box place-items-center"> Volume in Cubic Feet: <span class="font-bold text-success">{volumeCubicFeet.toFixed(2)}</span>  ft³</div>
    <div class="divider"></div>
    <!-- Display volume in cubic meters -->
    <div class="grid h-20 card bg-base-300 rounded-box place-items-center">Volume in Cubic Meters: <span class="font-bold text-success">{volumeCubicMeter.toFixed(2)}</span>  m³</div>
  </div>

  <div class="flex flex-col w-full justify-center items-center px-6">
    <!-- Input for length in inches -->
    <label class="form-control w-full max-w-xs">
      <div class="label">
        <span class="label-text">Length in Inches</span>
      </div>
      <input type="number" bind:value={lengthInches} placeholder="Type here" class="input input-bordered w-full max-w-xs" />
      <div class="label"></div>
    </label>
    <!-- Input for height in inches -->
    <label class="form-control w-full max-w-xs">
      <div class="label">
        <span class="label-text">Height in Inches</span>
      </div>
      <input type="number" bind:value={heightInches} placeholder="Type here" class="input input-bordered w-full max-w-xs" />
      <div class="label"></div>
    </label>
    <!-- Buttons for calculation and clearing -->
    <div class="flex  w-full justify-between items-center ">
      <button on:click={calculateVolume} class="btn btn-outline btn-success">Calculate</button>
      <!-- Call the clearValues function on click -->
      <button on:click={clearValues} class="btn btn-outline btn-error">Clear</button>
    </div>
  </div>

</div>
