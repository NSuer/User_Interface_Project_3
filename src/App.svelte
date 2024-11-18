<script>
  import CustomBlinkees from './CustomBlinkees.svelte';
  let currentPage = 'home';
  let x = 0, count1 = 0, count2 = 0, count3 = 0, count4 = 0, count5 = 0, count6 = 0, count7 = 0, count8 = 0, count9 = 0, count10 = 0, count11 = 0, count12 = 0, count13 = 0, count14 = 0, count15 = 0, count16 = 0;
  let productsCheck = true;

  function addtocart(item) {
    console.log(item)
    if (item == "count1") {
      cartTotal(count1)
    } else if (item == "count2") {
      cartTotal(count2)
    } else if (item == "count3") {
      cartTotal(count3)
    } else if (item == "count4") {
      cartTotal(count4)
    } else if (item == "count5") {
      cartTotal(count5)
    } else if (item == "count6") {
      cartTotal(count6)
    } else if (item == "count7") {
      cartTotal(count7)
    } else if (item == "count8") {
      cartTotal(count8)
    } else if (item == "count9") {
      cartTotal(count9)
    } else if (item == "count10") {
      cartTotal(count10)
    } else if (item == "count11") {
      cartTotal(count11)
    } else if (item == "count12") {
      cartTotal(count12)
    } else if (item == "count13") {
      cartTotal(count13)
    } else if (item == "count14") {
      cartTotal(count14)
    } else if (item == "count15") {
      cartTotal(count15)
    } else {
      cartTotal(count16)
    }
  }

  function cartTotal(increment) {
    for (let i = 0; i < increment ; i++) {
      x += 1;
    }
  }

  function incrementUp(val) {
    if (val == "count1") {
      count1 += 1;
    } else if (val == "count2") {
      count2 += 1;
    } else if (val == "count3") {
      count3 += 1;
    } else if (val == "count4") {
      count4 += 1;
    } else if (val == "count5") {
      count5 += 1;
    } else if (val == "count6") {
        count6 += 1;
    } else if (val == "count7") {
        count7 += 1;
    } else if (val == "count8") {
        count8 += 1;
    } else if (val == "count9") {
        count9 += 1;
    } else if (val == "count10") {
        count10 += 1;
    } else if (val == "count11") {
        count11 += 1;
    } else if (val == "count12") {
        count12 += 1;
    } else if (val == "count13") {
        count13 -= 1;
    } else if (val == "count14") {
        count14 += 1;
    } else if (val == "count4") {
        count15 += 1;
    } else {
        count16 += 1;
    }
    cartTotal("add");
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
    } else if (val == "count4") {
      if (count4 > 0) {
        count4 -= 1;
      }
    } else if (val == "count5") {
      if (count5 > 0) {
        count5 -= 1;
      }
    } else if (val == "count6") {
      if (count6 > 0) {
        count6 -= 1;
      }
    } else if (val == "count7") {
      if (count7 > 0) {
        count7 -= 1;
      }
    } else if (val == "count8") {
      if (count8 > 0) {
        count8 -= 1;
      }
    } else if (val == "count9") {
      if (count9 > 0) {
        count9 -= 1;
      }
    } else if (val == "count10") {
      if (count10 > 0) {
        count10 -= 1;
      }
    } else if (val == "count11") {
      if (count11 > 0) {
        count11 -= 1;
      }
    } else if (val == "count12") {
      if (count12 > 0) {
        count12 -= 1;
      }
    } else if (val == "count13") {
      if (count13 > 0) {
        count13 -= 1;
      }
    } else if (val == "count14") {
      if (count14 > 0) {
        count14 -= 1;
      }
    } else if (val == "count4") {
      if (count15 > 0) {
        count15 -= 1;
      }
    } else {
      if (count16 > 0) {
        count16 -= 1;
      }
    }
    cartTotal("remove");
  }

  function showProducts() {
    productsCheck = false;
  }
  function showHome() {
    productsCheck = true;
  }
  
  let cartItems = [
    { id: 1, name: "Item 1", price: 10.99, quantity: 1 },
    { id: 2, name: "Item 2", price: 15.49, quantity: 2 },
  ];

  const removeItem = (id) => {
    cartItems = cartItems.filter((item) => item.id !== id);
  };

  const updateQuantity = (id, quantity) => {
    cartItems = cartItems.map((item) =>
      item.id === id ? { ...item, quantity: quantity } : item
    );
  };
  $: total = cartItems.reduce(
    (sum, item) => sum + item.price * item.quantity,
    0
  );

</script>

<!-- Improved UI Changes  -->
<!-- Buy in Bulk Button -->
<!-- Removed Second Navigation Checkout Menu Option -->
<!-- Footer redesign -->

<header>
  <section style="position: relative; left: 1%; display: flex; flex-direction: row; gap: 20px;">
    <img src="src/assets/Blinkee-logo.webp" width=300 height=26 style="position: relative; right: 5px; top: 7px; cursor: pointer;" on:click={() => currentPage = 'home'}>
    <input placeholder="Search for...">
  </section>
  <nav>
    <button on:click={() => currentPage = 'home'}>Home</button> <!-- Added home button to navigation -->
    <button on:click={() => currentPage = 'products'}>Products</button>
    <!--<button>Checkout</button>-->
    <button on:click={() => currentPage = 'customBlinkees'}>Custom Blinkees</button>
    <button>Account</button>
    <!--<button>Contact</button> We don't need another contact button -->
    <button>About</button>
    <!-- <button>Menu Item</button> this button on the action page leads to coins?!? -->
    <section>
      <img src="src/assets/1413908.png" width=18 on:click={()=>currentPage = 'shoppingCart'}>
      <label for="shopping-cart">{x}</label>
    </section>
  </nav>
</header>
<main>
  {#if currentPage === 'home'}
    <div class="menu-row">
      <div class="menu-item">
        <img src="src/assets/Light-Up-Pirate-Rapier-Expandable-Sword-Main-350x350.webp" width=300>
        <h2 style="padding: 0; margin: 0;">Light Up Pirate Rapier Expandable Sword</h2>
        <div class="item-details">
          <section>
            <h4 style="line-height: 0px; padding: 0;">$7.69</h4>
            <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                <button class="increments" on:click={() => incrementDown("count1")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                <p style="padding: 0; margin: 0;">{count1}</p>
                <button class="increments" on:click={() => incrementUp("count1")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
            </section> 
            <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count1")}>Add to Cart</button>
          </section>
          <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
          <section>
            <h4 style="line-height: 0px;">As low as $4.89 Bulk</h4>
            <button style="cursor: pointer;">Buy in Bulk</button>
          </section>
        </div>
      </div>
      <div class="menu-item">
        <img src="src/assets/Light-Up-Expandable-Magic-Wizard-with-Prism-Ball-Main-350x350.webp" width=300>
        <h2 style="padding: 0; margin: 0;">Light Up Expandable Magic Wizard with Prism Ball</h2>
        <div class="item-details">
          <section>
            <h4 style="line-height: 0px; padding: 0;">$4.99</h4>
            <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                <button class="increments" on:click={() => incrementDown("count2")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                <p style="padding: 0; margin: 0;">{count2}</p>
                <button class="increments" on:click={() => incrementUp("count2")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
            </section> 
            <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count2")}>Add to Cart</button>
          </section>
          <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
          <section>
            <h4 style="line-height: 0px;">As low as $4.29 Bulk</h4>
            <button style="cursor: pointer;">Buy in Bulk</button>
          </section>
        </div>
      </div>
      <div class="menu-item">
        <img src="src/assets/Galactic-LED-Expandable-Green-Light-Saber-Sword0-350x350.webp" width=300>
        <h2 style="padding: 0; margin: 0;">Galactic LED Expandable Green Light Saber Sword</h2>
        <div class="item-details">
          <section>
            <h4 style="line-height: 0px; padding: 0;">$4.49</h4>
            <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                <button class="increments" on:click={() => incrementDown("count3")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                <p style="padding: 0; margin: 0;">{count3}</p>
                <button class="increments" on:click={() => incrementUp("count3")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
            </section> 
            <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count3")}>Add to Cart</button>
          </section>
          <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
          <section>
            <h4 style="line-height: 0px;">As low as $3.79 Bulk</h4>
            <button style="cursor: pointer;">Buy in Bulk</button>
          </section>
        </div>
      </div>
      <div class="menu-item-last">
        <img src="src/assets/LED-Shark-Light-Up-Saber-Sword-Main-350x350.webp" width=300>
        <h2 style="padding: 0; margin: 0;">LED Shark Light Up Saber Sword</h2>
        <div class="item-details">
          <section>
            <h4 style="line-height: 0px; padding: 0;">$8.49</h4>
            <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                <button class="increments" on:click={() => incrementDown("count4")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                <p style="padding: 0; margin: 0;">{count4}</p>
                <button class="increments" on:click={() => incrementUp("count4")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
            </section> 
            <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count4")}>Add to Cart</button>
          </section>
          <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
          <section>
            <h4 style="line-height: 0px;">As low as $6.59 Bulk</h4>
            <button style="cursor: pointer;">Buy in Bulk</button>
          </section>
        </div>
      </div>
    </div>
  {:else if currentPage === 'products'}
    <div class="products">
      <div class="row-1">
        <div class="menu-item">
          <img src="src/assets/NASA-Custom-Flashing-Blinky-Light-Pin-Technical-Drawing-350x276.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Custom LED Flashing Blinky Light Pins - LogoBlinkee.com</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">Starting at $1.44</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count5")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count5}</p>
                  <button class="increments" on:click={() => incrementUp("count5")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count5")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section style="position: relative; bottom: 10px;">
              <h4 style="line-height: 0px;">As low as N/A Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/black-light-feauxton-led-light-key-rings-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Black Light LED Light Keychain Flashlight</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">Starting at $0.99</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count6")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count6}</p>
                  <button class="increments" on:click={() => incrementUp("count6")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count6")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section style="position: relative; bottom: 10px;">
              <h4 style="line-height: 0px;">As low as $0.60 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/light-up-devil-horns-blue-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Light Up Devil Horns Blue</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">Starting at $1.79</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count7")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count7}</p>
                  <button class="increments" on:click={() => incrementUp("count7")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count7")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section style="position: relative; bottom: 10px;">
              <h4 style="line-height: 0px;">As low as $1.49 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
          <div class="menu-item-last">
            <img src="src/assets/Slingshot-LIght-Up-Orange-350x350.webp" width=300>
            <h2 style="padding: 0; margin: 0;">Slingshot Flying Helicopter with Multicolor LED</h2>
            <div class="item-details">
              <section>
                <h4 style="line-height: 0px; padding: 0;">Starting at $0.49</h4>
                <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                    <button class="increments" on:click={() => incrementDown("count8")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                    <p style="padding: 0; margin: 0;">{count8}</p>
                    <button class="increments" on:click={() => incrementUp("count8")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
                </section> 
                <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count8")}>Add to Cart</button>
              </section>
              <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
              <section style="position: relative; bottom: 10px;">
                <h4 style="line-height: 0px;">As low as $0.34 Bulk</h4>
                <button style="cursor: pointer;">Buy in Bulk</button>
              </section>
            </div>
          </div>
      </div>
      <div class="divider"></div>
      <div class="row-2">
        <div class="menu-item">
          <img src="src/assets/White-LED-Fiberoptic-Wand-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">White Fiber Optic Wand with White LEDs</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$1.89</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count9")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count9}</p>
                  <button class="increments" on:click={() => incrementUp("count9")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count9")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $1.49 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/SoftBubbleRings-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Light Up Soft Bubble Novelty Flashing Rings Pack of 24</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$28.44</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count10")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count10}</p>
                  <button class="increments" on:click={() => incrementUp("count10")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count10")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $23.99 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/WhiteCoasterLEDBase-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">White LED Switch Activated Bottle Base Light Display Drink Coaster</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$4.19</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count11")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count11}</p>
                  <button class="increments" on:click={() => incrementUp("count11")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count11")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $3.49 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item-last">
          <img src="src/assets/Light-Up-Silver-White-Flashing-Cowboy-Sequins-Hat-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Light Up LED Flashing Cowboy Hat with White Sequins</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$7.39</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count12")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count12}</p>
                  <button class="increments" on:click={() => incrementUp("count12")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count12")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $6.29 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
      </div>
      <div class="divider"></div>
      <div class="row-3">
        <div class="menu-item">
          <img src="src/assets/Mirror-Ball-Hooked-Earrings-350x318.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Groovy Disco Mirror Ball Earrings</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$1.49</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count13")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count13}</p>
                  <button class="increments" on:click={() => incrementUp("count13")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count13")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $1.14 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/RedHeartLEDBodyLightLapelPinMain-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Red Heart Flashing Battery Operated Body Light Lapel Pins</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$1.79</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count14")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count14}</p>
                  <button class="increments" on:click={() => incrementUp("count14")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count14")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $1.44 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item">
          <img src="src/assets/Silver-White-Non-LightUp-Sequin-Glove-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Non Light Up Jacko Thriller Beat It Billie Jean Right Hand Sequin Glove</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$2.49</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count15")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count15}</p>
                  <button class="increments" on:click={() => incrementUp("count15")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count15")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $2.19 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
        <div class="menu-item-last">
          <img src="src/assets/Flashing-Light-Up-Tunnel-Coaster-350x350.webp" width=300>
          <h2 style="padding: 0; margin: 0;">Infinite Illumination LED Tunnel Coaster</h2>
          <div class="item-details">
            <section>
              <h4 style="line-height: 0px; padding: 0;">$3.79</h4>
              <section style="position: relative; display: flex; flex-direction: row; justify-content: center; gap: 10px; width: 100%; align-items: center; margin-bottom: 10px;">
                  <button class="increments" on:click={() => incrementDown("count16")} style="cursor: pointer; padding: 2px 5px; border-radius: 20px; border: 2px solid black;">-</button>
                  <p style="padding: 0; margin: 0;">{count16}</p>
                  <button class="increments" on:click={() => incrementUp("count16")} style="cursor: pointer; padding: 3px 2px; border-radius: 20px; border: 2px solid black;">+</button>
              </section> 
              <button style="margin-bottom: 10px; cursor: pointer;" on:click={() => addtocart("count16")}>Add to Cart</button>
            </section>
            <div style="position: relative; bottom: 0px; height: 135px; width: 2px; background-color: black;"></div>
            <section>
              <h4 style="line-height: 0px;">As low as $3.09 Bulk</h4>
              <button style="cursor: pointer;">Buy in Bulk</button>
            </section>
          </div>
        </div>
      </div>
    </div>

  {:else if currentPage === 'customBlinkees'}
    <CustomBlinkees />
  {:else if currentPage === 'shoppingCart'}
    
    <div class="cart-container">
      <h1>Your Cart</h1>
      {#if cartItems.length === 0}
        <p>Your cart is empty!</p>
      {/if}

      {#each cartItems as item}
      <div class="cart-item">
        <p>{item.name}</p>
        <p>${item.price.toFixed(2)}</p>
        <input
          type="number"
          min="1"
          bind:value={item.quantity}
          on:input={() => updateQuantity(item.id, item.quantity)}
        />
        <button on:click={() => removeItem(item.id)}>Remove</button>
      </div>
    {/each}

    {#if cartItems.length > 0}
      <div class="checkout-section">
        <p>Total: ${total.toFixed(2)}</p>
        <button class="checkout-btn">Checkout</button>
      </div>
      {/if}
    </div>
  
  {/if}
</main>

<footer>
  <div class="upper-footer">
    <div style="position: relative; width: 100%; display: flex; flex-direction: row; justify-content: space-around;">
      <ul class="first-list">
        <!--<button>Home</button> Your home navigation shouldnt be on the bottom, it should be in the nav-->
        <button>About</button>
        <button>Return Policy</button>
        <button>Shipping Policy</button>
        <button>Coupon</button>
        <!--<button>Contact</button> Why have contact on this side but the phone and email on the other?-->
        <button>Blinkee.com Resellers and Dropshippers</button>
      </ul>
      <ul class="second-list">
        <p style="color: white; font-size: 95%; margin:0;">Contacts:</p>
        <button>415.261.0675</button>
        <button>Matt@Blinkee.com</button>
        <!--<button>My Account</button> Account in both? -->
        <!--<button>Checkout</button> Checkout in both? -->
      </ul>
      <ul class="third-list">
        <button>Cart</button>
        <button>Checkout</button>
        <button>Account</button>
        <button>Logout</button>
      </ul>
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
    font-family: 'Roboto', sans-serif;
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
    height: 4.5%;
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
    align-items: center;
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

    min-height: 66.1vh;
    margin-top: 3%;
    padding-top: 20px;
  }

  .menu-row {
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;

    margin-top: 35px;

    height: 100%;
    max-width: 100%;
  }

  .menu-item {
    position: relative;

    width: 20%;
    text-align: center;

    padding: 0 40px 0 0;
    min-height: 60vh;

    border-right: 1px solid rgb(0,0,0,0.4);
  }

  .menu-item-last {
    position: relative;

    width: 20%;
    text-align: center;

    min-height: 60vh;
    padding: 0 40px 0 0;
  }

  .menu-item button, .menu-item-last button {
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

  .upper-footer button {
    cursor: pointer;
  }

  .first-list {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    padding: 10px 0px;

    min-width: 25%;
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
    justify-content: space-evenly;
    padding: 10px 0px;
    text-align: center;

    min-width: 25%;
  }

  .second-list button {
    background-color: rgb(30,30,30);
    color: white;
    border: none;

    font-size: 95%;
  }

  .third-list {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    padding: 10px 0px;

    min-width: 25%;
  }

  .third-list button {
    background-color: rgb(30,30,30);
    color: white;
    border: none;

    font-size: 95%;
  }

  .lower-footer {
    text-align: center;
  }

  .products {
    position: relative;
    display: flex;
    flex-direction: column;
    
    align-items: center;
  }

  .row-1, .row-2, .row-3 {
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: end;

    padding: 25px 0;
  }

  .divider {
    position: relative;
    
    width: 90%;
    height: 1px;

    background-color: rgb(0,0,0,0.4)
  }

  main button:hover {
    background-color: rgb(230,230,230);
    cursor: pointer;
  }

  .item-details {
    display:flex; 
    flex-direction: row; 
    justify-content: center; 
    gap: 20px; 
    align-items: center;
  }


  .cart-container {
    width: 80%;
    margin: 20px auto;
    font-family: Arial, sans-serif;
    color: #333;
  }
  
  .cart-container h1 {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .cart-container .cart-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
  
  .cart-container .cart-item input {
    width: 50px;
    text-align: center;
  }
  
  .cart-container .cart-item button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .cart-container .cart-item button:hover {
    background-color: #0056b3;
  }
  
  .cart-container .checkout-section {
    text-align: right;
    margin-top: 20px;
  }
  
  .cart-container .checkout-section .checkout-btn {
    background-color: #28a745;
    color: #fff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .cart-container .checkout-section .checkout-btn:hover {
    background-color: #218838;
  }
  
</style>