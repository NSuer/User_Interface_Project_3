# User_Interface_Project_3
Members: Sam Weese, William Braun, Owen Richards, and Nathan Suer

# Link to your source code on github
https://github.com/NSuer/User_Interface_Project_3

# Link to the publicly hosted application
https://nsuer.github.io/User_Interface_Project_3/
(Our Pictures don't work, see video or download code to see them)

# Description of the project
Our redesign of Blinkee (https://blinkee.com/) focused on enhancing the user experience by streamlining the interface and reducing visual clutter. The primary goal was to create a clean, modern, and minimalist website that prioritizes user engagement while avoiding unnecessary distractions. The updated design ensures that users can seamlessly navigate the platform, easily find their desired products, and customize Blinkees without feeling overwhelmed. This redesign combines functionality with aesthetics to provide an enjoyable shopping experience for Blinkee’s audience, ensuring that the platform is both engaging and effective.

Key features of the redesign include:
- Simplified Layout: We reorganized the site structure to make navigation intuitive and visually appealing. The emphasis is on clarity and ease of use.
- Redesigned custom Blinkee Creator: A dedicated, user-friendly tool allows customers to design their own custom Blinkees, offering a personalized experience with minimal friction.

- TODO Double check me

# Design Work
## 1. Choose a UI to fix
We decided to fix the Blinkee website, https://blinkee.com/

On first glance, we noticed several things that could be improved, some of those are:
- "Qty Discount" Button - They displayed the price for this with the label "Bulk." They should use the same wording to keep correlation.
- Footer - The whole footer is a mess. It takes up half of the screen, two long vertical lists, duplicate navigation buttons (Checkout, My Account/Account), and the Home navigation only at the bottom.
- They added a Christmas theme to the home page that moves and it's very distracting, it's linked to their Christmas themed blinkees but why wouldn't that be on the main page?
- "Custom Blinkee" - Button in the navigation leads to a completely new website with no way to get back.
- Products Page - This page isn't structured overly well. Doesn't stick with the four per row theme of the main page and is somewhat hard to differentiate between the different items.

## 2. Redesign research, data, planning

Chosen Methods
- Expert heuristic evaluation
    - To complete this method, we will read through each of the linked articles on the “Heuristic evaluation” Canvas page. After reading through each of the heuristics, we will determine which are most applicable to our chosen website. We will then determine if each of the chosen guidelines is addressed by the current website. For those that are not yet addressed, we will figure out the best way to implement it in our redesign.

    - Chosen Heuristics
        - Visibility of System Status
            - This guideline is prevalent throughout the website, as it is always important to let the user know where they are. This guideline is addressed by the "You Are Here:" text on every page of the website (aside from the home page). However, when the user clicks on the "Custom Blinkees" menu item in the navigation bar, they are taken to a new website. While the site does look different, it can be a bit difficult to realize it is a completely new website at first. In this case, the user is not notified of where they are. In our redesign, we will either make the LogoBlinkee.com site be built into the original Blinkee.com website or have a message that shows the user was taken to a new website. 

        - User Control and Freedom
            - This guideline is prevalent any time the user starts a process or does an action. Blinkee.com does support the undo and redo buttons on one's search engine, but there are not many "exits" built into the site itself. On the checkout page, there is no clear cancel button. The user can adjust the quantity of an item being ordered or completely remove it, but navigating away from this page requires the user to either click "blinkee.com" after the "You Are Here:" text or use the navigation bar to access a different page. Another example of where this guideline needs to be addressed is what happens when the user clicks the "Custom Blinkee" menu item. This button takes the user to a completely different website with no options to return to Blinkee.com without pressing the undo button offered by the search engine. To address this guideline, we will include cancel, exit, or undo buttons on almost every page to ensure the user never gets stuck and always has a clear exit. 

- Observational study with a think aloud protocol
    - To complete this method, we will recruit at least three participants and have them complete a series of tasks on the current Blinkee website. Because this website could be used by a wide variety of people, we will attempt to have some variation in our participants, especially in terms of age. The set tasks could include things such as ordering a certain item, making a custom Blinkee, navigating the shopping cart, and more. We will record the screen as participants work through these tasks, and we will ask them to think aloud as they do so. After all of the participants complete the study, we will compare what they said while completing the tasks to best identify difficulty points. 

    - Tasks: 
        1. Add 3 "Multicolor Star Infinity Tunnel Necklaces" to the shopping cart
        2. Add at least 1 "Masquerade Silver Unlit Metallic Mask Mardi Gras" to the shopping cart
        3. Navigate to the shopping cart. From here, remove all of the "Multicolor Star Infinity Tunnel Necklaces: and add at least 1 "Masquerade Silver Unlit Metallic Mask Mardi Gras." Make sure these changes are reflected in the price of all the items in the shopping cart. 
        4. Navigate to the "Custom Blinkees" page. Start the process of creating a custom Blinkee by uploading an image to the correct page. Add at least one LED to the custom page and make the LED fade. Once finished with the custom Blinkee, return to the original website without using your search engine's browser. 
        5. Find the return policy for Blinkee.com and start a return. 

- System Usability Scale
    - To complete this method, we will make a questionnaire that contains all ten of the SUS statements. We will ask the participants from the observational study to complete this questionnaire after they finish with the tasks. We will then follow the steps outlined by the linked website on the Canvas page to score this UI and determine how good its usability is. This overall score, along with the scores for each of the individual statements, will help us evaluate the usability of the site and identify areas for improvement.

    - Questionnaire: https://docs.google.com/forms/d/e/1FAIpQLSf_jZzDSNIZvfFB4CkvMpjwsvOJp8bPbNUije5bH_2pf06zrQ/viewform?usp=sf_link

- Surprise Interviews
    - We asked 3 participants from the R21 UC Trains Voice team two questions: What do you like about this website? What do you dislike?
    - Interviewee one (Om)
        - I dislike the Blinkee logo coloring. It looks bad on a white background.
        - I like the rounded corners on buttons.
    - Interviewee two (Rey)
        - I dislike the white void at the top
        - Proceeded to leave before I could ask what things were good.
    - Inteviewee three (Gowtham)
        - I dislike the colors, its hard on the eyes. I dislike the URL display at the top, I dislike the customer reviews overview, I dislike the buttons being stacked, the stacking of the footer is ugly.
        - I like the sorting option being up front in the header. I dislike the header being stacked now that I look at it.


## 3. Sketch and get feedback
### Homepage
![Homepage](src/assets/Homepage.png)

### Products Page
![Products Page](src/assets/Products_Page.png)

### Item Listings
![Item Listing Examples](src/assets/Item_Listings.png)\
Three examples of how we could separate the standard and bulk buying processes. This would help clear confusion of the actual price.

### Product Separation
![Product Seperation Examples](src/assets/Product_Seperation.png)\
Three examples of how popular websites, Amazon, Target, and Ebay, separate their items.

### Figma
![Figma Picture](src/assets/Figma.png)\
We also created a digital sketch using Figma of the homepage. You can use this link to view it: [link](https://www.figma.com/design/YuXij3fd8w6rPIs51JV1G0/Figma-basics?node-id=601-9&t=cAYFKjjlQhCwvhNZ-1)

## 4. Feedback
Sketch Feedback

Homepage:
Of the people I showed the sketches too, all but one mentioned they were happy to see the moving UI on the current Blinkee webpage was gone. I mentioned to all of them that I didn't include the footer in this sketch and explained it would be smaller and separated into categories, to which they all agreed with the change.

Products Page:
They all agreed in adding dividers/spacers or something similar to split the items apart. They also agreed in adding "Home" to the navigation.

Item Listing:
Of the three sketches, two said they liked the middle one where the standard and bulk buying process are separated vertically. The last one said they preferred it stacked in the far right sketch. 

Product Separation:
They all agreed that there should be some separation between the product and the background, unlike the actual website, but all had different answers of their preferred styling. One person said they preferred the left to keep things simple. Another said the dividers would allow for more separation and would be less confusing to the user. The last said although the backgrounds change, they would like a navigation menu on the left side to easily sort through all of the products on the webpage.

# Description of the interface in detail 
The redesigned Blinkee website interface is thoughtfully structured to provide users with a seamless and intuitive shopping experience. The interface consists of three main components: the Custom Blinkee tool, Product Pages, and the Shopping Cart. The redesigned interface achieves a balance of functionality and simplicity, ensuring an intuitive and enjoyable user journey across all features.

- Custom Blinkee Tool
    - Interactive Design Features: Users can upload their own artwork or images to create personalized Blinkees. The tool displays a preview of the customization process.
    - Interactive Dot System: Red dots on the displayed image allow users to specify customization locations, enabling precise placement for their designs.
    - Animation Options: Buttons at the bottom of the tool provide controls for dynamic effects, such as "Make it Flash" or "Make it Fade," ensuring flexibility in customization. Users can also reset their design to the default state with the "Reset" button.
    - Color Selection: A palette of colors is available for users to apply to their customized Blinkees, offering a wide range of creative options.

- Product Pages
    - Simplified Product Display: Products are arranged in a clean grid layout, each displayed within a bordered card for clear differentiation.
    - Detailed Product Information: Each product card includes the following:
        - A product image for visual reference.
        - A concise product name and description.
        - Pricing details, with options for single purchase or bulk orders.
        - "Add to Cart" and "Buy in Bulk" buttons for easy interaction.
    - Quantity Selector: Users can adjust the number of items they want to purchase directly on the product card using intuitive increment and decrement buttons.

- Shopping Cart
    - Minimalist Cart View: The shopping cart page is designed with a focus on clarity. It displays a list of selected items along with their corresponding prices.
    - Remove Items Feature: Users can remove items from the cart with a dedicated "Remove" button.
    - Checkout Overview: The cart summary includes a total price calculation at the bottom, along with a prominently displayed "Checkout" button for proceeding to payment.

- Additional Features
    - Navigation Menu: A fixed top navigation bar provides access to key pages, including Home, Products, Custom Blinkees, Account, and About.
    - Footer Links: The footer contains quick links to policies, FAQs, and contact information, ensuring all essential resources are readily accessible.

- TODO Double check me

# Implementation of this application 

- TODO I need someone to do this 

# Use of AI
- I (Nathan) use github copilot. I use it as more of an autocomplete, rather than it generating stuff.
- Used ChatGPT to make our description better. I used the prompt: "Make this more fleshed out our rediesign of Blinkee (https://blinkee.com/) looked to decrease the clutter on the screen and make a more simplsitic and non-distracting website. Users can add items to the cart and create custom blinkees."
- Used ChatGPT to make our description of the interface in detail better. I used the prompt and gave it pictures of our interface :"I now need a Description of the interface in detail. The features are custom blinkee, product pages, and shopping cart."

- TODO Double check me

# Future work
Obviously the work is never finished. We didn't have enough time to implement all we wanted . Here is a list of things we would implement if we had more time.
- "Buy in bulk" working and interactive. We would've liked to have a slider that would automatically shange the price given the quantity you order.
- Custom Blinkees having more options and an order feature.
- Adding more products from the original website 

TODO Double check me and add some - Nate

# Demo Video 

- TODO I need someone to do this 