# Shopify Developer Technical Assessment Submission

**Website:** https://gustavo-test-store-svrvdlf7.myshopify.com/

**Password:** `skaybu`

**Test product:** https://gustavo-test-store-svrvdlf7.myshopify.com/products/the-collection-snowboard-liquid

I’d like to walk you through the full process I followed to complete the assessment, as well as a few additional improvements and recommendations I identified along the way.

I started by confirming access to the Shopify development store and the Figma file, then reviewed the requirements to understand the expected scope and implementation approach.

After accessing the store, I downloaded the theme and set it up locally using Shopify CLI. I also connected the project to a public GitHub repository:

https://github.com/gabo5612/Shopify-Theme

I created a workflow with separate branches for `preview` and `master`, allowing development work to happen safely before being merged into the main branch. This approach provides a rollback strategy and helps prevent issues from affecting the live theme or the customer experience.

## PDP Design and Theme Implementation

For the PDP design, I reviewed the Figma file and rebuilt the layout in code with responsiveness and maintainability in mind. Some sections in the Figma file appeared to be image-based, which limited flexibility for responsive behavior and visual control.

Because of that, I used the tool Stitch to design a visual reference and recreated the structure directly in Liquid, CSS, and theme settings so it could behave properly across screen sizes.

Once the main PDP structure was in place, I focused on the requested variant-based functionality.

## Variant Picker Implementation

The first implementation was the icon/color swatch variant picker. I connected the product variants to a visual selector so customers can choose the product based on the available color options.

## Variant-Based Content Card

The second implementation was adding more value to each variant. In the original design, there was text below the purchase buttons that did not add much dynamic value. I moved that concept into a variant-based content card and created three new fields:

* Card Subheading
* Card Heading
* Card Description

These fields can change depending on the selected product variant, allowing the merchant to add more relevant messaging for each specific variant.

## Technical Specification Table

I also implemented the requested technical specification table for the product page. I used a similar architecture to the variant content cards and created the following variant metafields:

* Snowboard Board Type
* Snowboard Length
* Snowboard Flex Rating
* Snowboard Profile
* Snowboard Core Material
* Snowboard Base
* Snowboard Skill Level
* Snowboard Terrain

These metafields are independent from each other, so the merchant does not need to complete every field for the section to work. If only part of the information is available, the specification section will still display the available technical information cleanly.

## Checkout Value Recommendation

For the checkout value recommendation, since the client is on Shopify Plus and wants to improve the checkout experience without increasing expenses, I would recommend using Shopify’s native checkout extensibility tools, especially the Shopify Checkout Blocks app.

Checkout Blocks is a Shopify-owned solution that allows Plus merchants to customize the checkout experience without building a custom app or relying on paid third-party checkout apps. With it, the client can add value through content blocks, custom fields, display rules, and delivery/payment customizations.

Some recommendations include:

### 1. Add trust-building content in checkout

The client can display useful information such as return policy details, warranty information, secure checkout messaging, delivery expectations, customer support contact details, or product care instructions.

These blocks can help reduce friction and increase buyer confidence.

### 2. Add conditional messaging

Checkout messaging can be personalized depending on cart value, product type, customer tags, or shipping location.

For example, if the cart is close to a free shipping threshold, the checkout can display a message encouraging the customer to add more items.

### 3. Improve shipping and payment clarity

Using Checkout Blocks, the client can reorder, rename, or hide delivery and payment methods when needed.

This can simplify checkout and prevent customers from seeing irrelevant options.

### 4. Add custom fields when useful

If the client needs to collect extra information such as delivery notes, gift messages, or special instructions, this can be handled directly in checkout without adding another paid app.

### 5. Improve the Thank You and Order Status pages

Checkout Blocks can also be used to add post-purchase value, such as support information, product care instructions, cross-sell messaging, loyalty messaging, or social/community links after the order is placed.

## Customer Tagging and Shopify Flow Automation

For the customer tagging requirement, I created a Shopify Flow-based structure to automatically identify and segment high-value customers from California.

I created four workflows:

### 1. Tag high-value customer on order created

**Trigger:** Order created

**Purpose:** When an order meets the defined criteria, the customer is tagged as a high-value customer.

### 2. Tag possible high-value customer on signup from California

**Trigger:** Customer created

**Purpose:** When a new customer signs up from California, the customer is tagged as a possible high-value customer.

### 3. Send 10% discount to possible high-value customers

**Trigger:** Customer tags added

**Purpose:** When a customer receives the possible high-value tag, a 10% discount incentive can be sent to encourage the first purchase.

**Note:** For a complete production implementation, this workflow would ideally be connected to a tool such as Klaviyo in order to send targeted email campaigns and improve conversion tracking.

### 4. Convert possible high-value customer to high-value customer on first purchase

**Trigger:** Order created

**Purpose:** When a customer tagged as a possible high-value customer completes their first purchase, the workflow updates their segmentation and converts them into a high-value customer.

## Customer Segments

I also created two customer segments:

* High Value Customers
* Possible High Value Customers

These segments are based on customer tags, making it easier for the client to use them later for marketing, reporting, loyalty programs, or personalized customer journeys.

## Additional Recommendations

With these implementations, I believe the requested scope has been completed. However, I also see several opportunities to continue improving the store beyond the initial requirements.

My next recommendations would be to review and improve the technical SEO structure, since organic search is one of the most cost-effective ways to attract customers.

I would also optimize performance with the goal of reaching a 90+ score on both desktop and mobile whenever possible.

After that, I would review the store’s customer journey, identify conversion opportunities, and collaborate with the marketing team to prepare the site for future campaigns with proper tracking and performance measurement.

## Additional Note

Thank you again for your consideration. I appreciate the opportunity and look forward to your feedback.

Best regards,
Gabriel

