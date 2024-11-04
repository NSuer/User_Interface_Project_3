<script>
  let x = 0, count1 = 1, count2 = 1, count3 = 1, count4 = 1;

  function addtocart() {
    x += 1;
  }

  function incrementUp(val) {
    console.log(val)
    if (val == "count1") {
      count1 += 1;
    } else if (val == "count2") {
      count2 += 1;
    } else if (val == "count3") {
      count3 += 1;
    } else {
      count4 += 1;
    }
    
  }

  function incrementDown(val) {
    
    if (val == "count1") {
      if (count1 > 0) {
        count1 -= 1;
      }
    } else if (val == "count2") {
      if (count2 > 0) {
        count2 -= 1;
      }
    } else if (val == "count3") {
      if (count3 > 0) {
        count3 -= 1;
      }
    } else {
      if (count4 > 0) {
        count4 -= 1;
      }
    }
  }
</script>

<header>
  <section style="position: relative; left: 1%; display: flex; flex-direction: row; gap: 20px;">
    <img src="src/assets/Blinkee-logo.webp" width=300>
    <input placeholder="Search for...">
  </section>
  <nav>
    <button>Account</button>
    <button>Checkout</button>
    <button>Custom Blinkees</button>
    <button>Products</button>
    <button>Contact</button>
    <button>About</button>
    <button>Menu Item</button>
    <section>
      <img src="src/assets/1413908.png" width=15>
      <label for="shopping-cart">{x}</label>
    </section>
  </nav>
</header>
<main>
  <div class="menu-row">
    <div class="menu-item">
      <img src="src/assets/Light-Up-Pirate-Rapier-Expandable-Sword-Main-350x350.webp" width=300>
      <h4 style="line-height: 0px;">As low as $4.89 Bulk</h4>
      <section style="position: relative; display: flex; flex-direction: row; gap: 10px; margin: auto; width: 23%; align-items: center; line-height: 0px;">
        <button class="increments" on:click={() => incrementDown("count1")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 1px solid black;">-</button>
        <p>{count1}</p>
        <button class="increments" on:click={() => incrementUp("count1")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 1px solid black;">+</button>
      </section> 
      <h2>Light Up Pirate Rapier Expandable Sword</h2>
      <h4 style="line-height: 0px;">$7.69</h4>
      <button style="margin-bottom: 10px; cursor: pointer;">Add to Cart</button><br>
      <button style="cursor: pointer;">Buy in Bulk</button>
    </div>
    <div class="menu-item">
      <img src="src/assets/Light-Up-Expandable-Magic-Wizard-with-Prism-Ball-Main-350x350.webp" width=300>
      <h4 style="line-height: 0px;">As low as $4.29 Bulk</h4>
      <section style="position: relative; display: flex; flex-direction: row; gap: 10px; margin: auto; width: 23%; align-items: center; line-height: 0px;">
        <button class="increments" on:click={() => incrementDown("count2")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 1px solid black;">-</button>
        <p>{count2}</p>
        <button class="increments" on:click={() => incrementUp("count2")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 1px solid black;">+</button>
      </section> 
      <h2>Light Up Pirate Rapier Expandable Sword</h2>
      <h4 style="line-height: 0px;">$4.99</h4>
      <button style="margin-bottom: 10px; cursor: pointer;">Add to Cart</button><br>
      <button style="cursor: pointer;">Buy in Bulk</button>
    </div>
    <div class="menu-item">
      <img src="src/assets/Galactic-LED-Expandable-Green-Light-Saber-Sword0-350x350.webp" width=300>
      <h4 style="line-height: 0px;">As low as $3.79 Bulk</h4>
      <section style="position: relative; display: flex; flex-direction: row; gap: 10px; margin: auto; width: 23%; align-items: center; line-height: 0px;">
        <button class="increments" on:click={() => incrementDown("count3")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 1px solid black;">-</button>
        <p>{count3}</p>
        <button class="increments" on:click={() => incrementUp("count3")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 1px solid black;">+</button>
      </section> 
      <h2>Light Up Pirate Rapier Expandable Sword</h2>
      <h4 style="line-height: 0px;">$4.49</h4>
      <button style="margin-bottom: 10px; cursor: pointer;">Add to Cart</button><br>
      <button style="cursor: pointer;">Buy in Bulk</button>
    </div>
    <div class="menu-item">
      <img src="src/assets/LED-Shark-Light-Up-Saber-Sword-Main-350x350.webp" width=300>
      <h4 style="line-height: 0px;">As low as $6.59 Bulk</h4>
      <section style="position: relative; display: flex; flex-direction: row; gap: 10px; margin: auto; width: 23%; align-items: center; line-height: 0px;">
        <button class="increments" on:click={() => incrementDown("count4")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 1px solid black;">-</button>
        <p>{count4}</p>
        <button class="increments" on:click={() => incrementUp("count4")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 1px solid black;">+</button>
      </section> 
      <h2>Light Up Pirate Rapier Expandable Sword</h2>
      <h4 style="line-height: 0px;">$8.49</h4>
      <button style="margin-bottom: 10px; cursor: pointer;">Add to Cart</button><br>
      <button style="cursor: pointer;">Buy in Bulk</button>
    </div>
  </div>
</main>
<footer>
  <div class="upper-footer">
    <div style="position: relative; width: 100%; display: flex; flex-direction: row; justify-content: space-evenly;"> <!-- This is prob just gonna get deleted after our changes bc it looks really bad-->
      <ul class="first-list">
        <button>Home</button>
        <button>About</button>
        <button>Return Policy</button>
        <button>Shipping Policy</button>
        <button>Contact</button>
        <button>Cart</button>
        <button>Checkout</button>
        <button>Account</button>
        <button>Blinkee.com Resellers and Dropshippers</button>
      </ul>
      <ul class="second-list">
        <button>415.261.0675</button>
        <button>Matt@Blinkee.com</button>
        <button>Logout</button>
        <button>My Account</button>
        <button>Checkout</button>
        <button>Coupon</button>
      </ul>
      <ul></ul>
    </div>
  </div>
  <div class="lower-footer">
    <p>Copyright © 2024 - 2124 Blinkee.com, LLC® <br> All rights reserved.</p>
  </div>
</footer>

<style>
  :global(body) {
    background-color: rgb(240,240,240);

    color: black;

    width: 100%;
    font-family: 'Roboto', sans-serif
  }

  header {
    position: fixed;
    z-index: 1;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;

    background-color: white;

    width: 100%;
    height: 6%;
    top: 0px;
    padding-top: 10px;
    padding-bottom: 10px;
    border-bottom: black 1px solid;
  }

  nav {
    position: relative;
    right: 2%;
    display: flex;
    flex-direction: row;
  }

  nav button {
    background-color: white;
    color: black;
    border: none;

    font-size: 100%;
    padding-right: 20px;
    max-width: fit-content;

    cursor: pointer;
  }

  input {
    position: relative;

    background-color: white;
    height: 35px;
    padding-left: 10px;
    width: 150%;

    border: 2px solid rgb(0,0,0,0.2);
    color: black;
    font-size: 130%;
  }

  main {
    position: relative;
    margin-top: 4%;
    padding-top: 20px;
  }

  .menu-row {
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;

    margin-top: 20px;
    max-width: 100%;
  }

  .menu-item {
    position: relative;

    width: 20%;
    text-align: center;
  }

  .menu-item button {
    position: relative;

    font-size: 140%;
    background-color: white;
    color: black;
    border: 2px solid black;
    padding: 5px 10px;

    border-radius: 5px;
  }

  footer {
    position: relative;
    top: 20px;
    background-color: white;
    padding-bottom: 1px;
  }

  .upper-footer {
    background-color: rgb(30,30,30);
  }

  .first-list {
    display: flex;
    flex-direction: column;
    padding: 20px 0px;
  }

  .first-list button {
    background-color: rgb(30,30,30);
    color: white;
    border: none;

    font-size: 95%;
  }

  .second-list {
    display: flex;
    flex-direction: column;
    padding: 20px 0px;
  }

  .second-list button {
    background-color: rgb(30,30,30);
    color: white;
    border: none;

    font-size: 95%;
  }

  .lower-footer {
    text-align: center;
  }
</style>