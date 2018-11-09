
<!-- .slide: data-background="#020203" -->

<span class="menu-title" style="display: none">Introduction</span>

<!-- .slide: data-transition="none" -->

<div class="west">
![Image](./assets/md/assets/browser-logos.gif)
</div>

<div class="east">
<span style="font-size: 2em">NEW <span style="color: #e49436">KIDS</span> IN<br><span style="color: #e49436">BROWSER</span>LAND</span>
<br><br>
<i class="fa fa-plug" aria-hidden="true"> </i> Supercharge your web apps<br>using the new browser APIs <i class="fa fa-bolt" aria-hidden="true"> </i>
</div>

Note:
Hello everyone! Today we'll talk about some of the new web APIs that have been recently added to the browser and how you can leverage them to build better experiences for your web users.

---
<!-- .slide: data-background="black" -->


<div class="west">
<span class="bio-about">Software Engineer at <a href="https://meesho.com/tech" target="_blank" rel="noopener noreferrer">Meesho</a><br>Obsessed with Sindre's <a href="https://github.com/sindresorhus/awesome" target="_blank" rel="noopener noreferrer">`awesome`</a> lists</span>
<br><br><br>
<i class="fa fa-terminal fa-3x bio-fa" aria-hidden="true"> geek</i>
<br><br><br>
<span class="bio-about">Open Source Contributor at Night<br>Co-Organizer at <a href="https://www.meetup.com/vue-bangalore/" target="_blank" rel="noopener noreferrer">Vue Bangalore</a></span>
</div>

<div class="east bio">
<span class="bio-headline">Swapnil Agarwal</span>
<br>
<span class="bio-byline"><a href="https://github.com/swapagarwal" target="_blank" rel="noopener noreferrer"><i class="fa fa-github pad-fa" aria-hidden="true"> </i></a> swapagarwal <a href="https://twitter.com/SwapAgarwal" target="_blank" rel="noopener noreferrer"><i class="fa fa-twitter pad-fa" aria-hidden="true"> </i></a></span>
<br>
![Image](./assets/md/assets/avatar.jpg)
<br>
<span class="bio-tagline">That swag guy! <a href="http://devswag.io/" target="_blank" rel="noopener noreferrer">devswag.io</a></span>
</div>

Note:
My name is Swapnil and I'm a software engineer at Meesho. Prior to that, I worked for 2 years at Amazon. I'm passionate about open-source sustainability and helping people start their open-source journey in general by lowering the entry barrier. If any of this excite you as well, I'd love to connect and hear your thoughts. You can find me on social media, by the handle swapagarwal.

---
<!-- .slide: data-background-image="./assets/md/assets/new_apis_are_coming!.jpg" data-background-size="auto 80%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
Back to the topic! Brace yourselves, Memes are coming.
Sorry, I meant new browser APIs are coming!

---

## Sneak Peek

- Intersection Observer API
- Credential Management API
- Network Information API
- Web Share API
- Device Memory API
- Payment Request API

Note:
Here's a sneak peek of the APIs that we'll be talking about today.

---

# Let's Start!

Note:
Without further delay, let's dive right in!



---
<!-- .slide: data-background-image="./assets/md/assets/lazy_loading.jpg" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
So, have you ever written JavaScript to enable infinite scrolling or to lazy-load images that appear below the fold?

If you're like me, you did this by listening for scroll events and requesting an element's `scrollTop` property or calling `getBoundingClientRect()` on an element. You forced the browser to stop everything and repeatedly recalculate the layout. You suffered. Your users suffered. It was a dark time.

Guess what? The dark times are now over! Introducing the glorious Intersection Observer API...

---

### Intersection Observer API

This API lets you know when an observed element enters or exits the browser's viewport (user's visible area of a web page).

Note:
This is a relatively new web API that provides easy-to-use, efficient tools for detecting changes to a DOM element's visibility within the browser viewport or within another element. No more reflow. No more suffering. None.

---
<!-- .slide: data-background-image="./assets/md/assets/intersection-observer-demo.gif" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="west">
<span style="font-size: 2em">Demo</span>
</div>

Note:
Here'a quick demo of the API in action. The top banner displays the answer to the question, "Is the green box in view?". As you can see, the API handles visibility of elements inside iframes too.

---
<!-- .slide: data-background-image="./assets/md/assets/intersection-observer-threshold.gif" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="east">
Thresholds = <br>[0, 0.25, 0.5,<br>0.75, 1]
</div>

Note:
But wait... There's more! The API also supports an option of specifying a list of thresholds. Your callback will be called every time the `intersectionRatio` crosses one of these values. The default value for threshold is [0], which explains the default behavior. If we change threshold to [0, 0.25, 0.5, 0.75, 1], we will get notified every time an additional quarter of the element becomes visible.

---

### Use Cases

<ul class=" ">
<li class="fragment  ">Lazy Loading</li>
<li class="fragment  ">Reporting of visibility of advertisements in order to calculate ad revenues</li>
<li class="fragment  ">Better Navigation Bar</li>
<li class="fragment  ">Check which feed cards are seen by user to avoid showing duplicate cards</li>
</ul>

Note:

As for the use cases,
- You can decide whether or not to perform resource-intensive tasks (like animation) based on whether the user will see the result or not.
- Reporting of visibility is important in case of advertisements for revenue calculation.
- Imagine a navigation bar that allows you to jump between sections on a page. While you are scrolling through the page, the link to the section that's currently in the viewport can be highlighted using this API.
- You can also provide an improved user feeds experience. Check which feed cards are seen by user to avoid showing duplicate cards.

---
<!-- .slide: data-background-image="./assets/md/assets/intersection-observer.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
https://caniuse.com/#feat=intersectionobserver
</div>

Note:
This API is already supported by major browsers like Chrome, Firefox, Edge, etc.




---
<!-- .slide: data-background-image="./assets/md/assets/my-name-is-yu.jpg" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
To provide a sophisticated user experience, it's important to help users authenticate themselves to your website. Authenticated users can interact with each other using a dedicated profile, sync data across devices, or process data while offline; the list goes on and on. But creating, remembering and typing passwords tends to be cumbersome for end-users, especially on mobile screens. It can even lead them to re-using the same passwords on different sites, which, of course, is a security risk.

---

### Credential Management API

This API lets a website store and retrieve password credentials.

Note:
Enter the Credential Management API. It gives developers programmatic access to a browser's credential manager and helps users sign-in more easily.

---
<!-- .slide: data-background-image="./assets/md/assets/credential-management.png" data-background-size="95% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">API Spec</span>
</div>

Note:
Here are the API specifications. The first 3 are simple CRUD operations. The last one is a bit interesting. When you call `preventSilentAccess`, the browser ensures that user mediation is required on the next credential access request, effectively "logging out" the user.

---
<!-- .slide: data-background-image="./assets/md/assets/credential-management-demo.gif" data-background-size="auto 90%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="west">
<span style="font-size: 2em">Demo</span>
</div>

Note:
Let's take a look at a user flow after integrating with this API.
The user visits the website. Notice the bottom blue banner to see how the site attempts to sign-in the user automatically. Note that this would work seamlessly only when the `preventSilentAccess` is set to `false`.

---

### Use Cases

<ul class=" ">
<li class="fragment  ">Removes friction from sign-in flows</li>
<li class="fragment  ">One tap sign-in with account chooser</li>
<li class="fragment  ">Stores and syncs credentials</li>
</ul>

Note:

- The most exciting part of using Credential Management API is the auto sign-in. Users can be automatically signed back into a site even if their session has expired or they saved credentials on another device.
- Allows one tap sign in with account chooser - Users are presented with a native account chooser.
- Your application can store either a username and password combination or even federated account details. These credentials can be synced across devices by the browser.

---
<!-- .slide: data-background-image="./assets/md/assets/credential-management.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
https://caniuse.com/#feat=credential-management
</div>

Note:
This is supported on UC and Chrome browsers, which account for more than 70% combined usage in India.




---
<!-- .slide: data-background-image="./assets/md/assets/is_impossible_to_read_on_my_smartphone.jpg" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
Responsive Web Design has revolutionized the web. A single site can adapt its layout when viewed on a range of different devices and screens. All that's required is a few media queries to detect the screen size and load alternative CSS.

However, using the screen size to detect browser capabilities is similar to judging a car's speed by looking at its radio. Modern smartphones and tablets have increasingly large resolutions and will happily show a typical desktop view. If that view adds numerous fonts, images or other assets, the mobile user may receive a degraded — and expensive — experience when they're on a slower or metered connection.

---

### Network Information API

This API lets you retrieve the current network type and monitor for network type changes.

Note:
The Network Information API provides a solution here. It indicates whether the user is on a metered connection (such as pay-as-you-go) and provides an estimate of bandwidth. Using this information, it's possible to conditionally load images, videos, fonts and other resources. At a very basic level, you could override a media query to ensure the mobile layout is retained on a limited network.

---

### Example

Write connection-aware components, rendering different elements for different speeds. For example, a <Media /> component in a news article might output:
<ul class=" ">
<li class="fragment  ">offline: a placeholder with alt text</li>
<li class="fragment  ">2g / reduced data mode: a low-resolution image, ~30kb</li>
<li class="fragment  ">3g: a high resolution retina image, ~200kb</li>
<li class="fragment  ">4g: a HD video ~1.8MB</li>
</ul>

Note:
- You can use service workers to return hi-res or lo-res images depending on the connection.

---
<!-- .slide: data-background-image="./assets/md/assets/network-information-demo.jpg" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
- This is how a network-responsive component may look like for different users.

---
<!-- .slide: data-background-image="./assets/md/assets/network-information-preload.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Preload Assets</span>
</div>

Note:
- Determine whether to preload resource-intensive assets, such as video, based on network connection (deciding to not preload assets if they're over cellular).

---
<!-- .slide: data-background-image="./assets/md/assets/network-information-monitor.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Monitor</span>
</div>

Note:
- Conditionally load images, videos, fonts and other resources based on whether the user is on a metered connection (such as pay-as-you-go) and his bandwidth.

---
<!-- .slide: data-background-image="./assets/md/assets/network-information.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
https://caniuse.com/#feat=netinfo
</div>

Note:
This is supported on Chrome and Firefox for Android. Support for other platforms is coming soon.


---
<!-- .slide: data-background-image="./assets/md/assets/halfway.png" data-background-size="100% 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
3 APIs down, 3 more to go!

---

### How do you add sharing functionality on a website today?

Note:
If you've ever built a website and needed the ability to share to a social network, you know that it's not as easy as it first seems. In order to add basic share functionality, you often need to include a third party script and become familiar with its API. Not to mention the fact that third party scripts can have a detrimental effect on the page load performance of your site. As you add more and more sharing links, you'll quickly start to collect a lot of scripts.

Web developers have always been jealous of the ability that native developers have that enables them to tap into the sharing capabilities of a device. Sharing between native apps on your device is so easy, but there isn't any reason why it shouldn't be easy for web developers!

---

### Web Share API

This API offers a simple way to allow websites to invoke the native sharing capabilities of the host platform.

Note:
This is where the Web Share API comes into play. It allows websites to invoke the native sharing capabilities of the host platform directly from the web. The advantages include:
- The API is simple to use.
- You can share to any installed apps, social networks, and even websites.
- And the best thing is, that It provides a uniform and familiar user-experience.

---
<!-- .slide: data-background-image="./assets/md/assets/web-share.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Code Sample</span>
</div>

Note:
Here's a code sample for using the Web Share API. As you can see, the API is really simple and provides just one method - navigator.share(data)
where `data` can contain `title`, `text`, and `url`

---
<!-- .slide: data-background-image="./assets/md/assets/web-share-demo.gif" data-background-size="auto 90%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="west">
<span style="font-size: 2em">Demo</span>
</div>

Note:
Let's take a look at a demo integration of this API. Notice the familiar way of sharing data around.

---
<!-- .slide: data-background-image="./assets/md/assets/web-share.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
https://caniuse.com/#feat=web-share
</div>

Note:
This API is rolled out to Chrome and is in Safari's Preview version.


---

### Let's talk about memory

Note:
The range of capabilities of devices that can connect to the web is wider today than it's ever been before. The same web application that's served to a high-end desktop computer may also be served to a low-powered phone, watch, or tablet, and it can be incredibly challenging to create compelling experiences that work seamlessly on any device.


---
<!-- .slide: data-background-image="./assets/md/assets/are_widely_used_in_emerging_markets.jpg" data-background-size="auto 100%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


Note:
Low memory devices devices (under 512MB, 512MB-1GB) are widely used in emerging markets.

---

### Device Memory API

This API returns the amount of device memory (RAM) on a user's machine in gigabytes.

Note:
The Device Memory API is a new web platform feature aimed at helping web developers deal with the modern device landscape. It adds a read-only property to the navigator object, navigator.deviceMemory, which returns how much RAM the device has in gigabytes, rounded down to the nearest power of two.

---
<!-- .slide: data-background-image="./assets/md/assets/device-memory.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Code Sample</span>
</div>

Note:
Here, you can see business logic being implemented depending on whether the device has less than 1GB of RAM or more.

---

### Use Cases

<ul class=" ">
<li class="fragment  ">Serve a "lite" app to users on low-end devices</li>
<li class="fragment  ">Add context to metrics</li>
</ul>

Note:

- Enable developers to tailor content at runtime in accordance with hardware limitations. For example, developers can serve a "lite" app to users on low-end devices, resulting in better experiences and fewer frustrations.
- Add context to metrics, such as the amount of time a task takes to complete in JavaScript, through the lens of device memory. This will result in a better understanding of how device memory correlates with user behavior, conversions, or other metrics important to your business.

---
<!-- .slide: data-background-image="./assets/md/assets/device-memory.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory#Browser_compatibility" target="_blank" rel="noopener noreferrer">Reference</a>
</div>

Note:
As for the browser support, Chrome and Opera already support this API.




---
<!-- .slide: data-background-image="./assets/md/assets/payment-request-without.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
Typical Checkout Form
</div>

Note:
Buying things online can be a frustrating process, especially on mobile. Even if the pages are well designed, there's a lot of information required: Our contact information, shipping and billing addresses, shipping option and card details. If you've ever just given up sometimes, you're in the majority.

The Baymard Institute took an average across 37 different studies and found that 69% of shopping carts are abandoned.

Unsurprisingly, the figures are worse on mobile, where the smaller screen and lack of a physical keyboard can make input slower. The abandonment rate on mobile can be as high as 84% or more! With the rise of mobile browsing over recent years, this means the overall problem has been getting worse. For e-commerce sites, these abandoned carts are costing a huge amount of money. Business Insider estimated $4 trillion worth of merchandise would be abandoned in one year.

---

### Payment Request API

This API is meant to reduce the number of steps needed to complete a payment online, potentially doing away with (long) checkout forms.

Note:
Thankfully, the web is fighting back against this problem. The "Web Payments" W3C Working Group has been busy working on "a revolution in payments on the web", developing new standards to help make online payments much easier. Payment Request API is a step forward in that direction. It aims to reduce the number of steps needed to complete a payment online, potentially doing away with checkout forms.

---
<!-- .slide: data-background-image="./assets/md/assets/payment-request-demo.gif" data-background-size="auto 90%" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="west">
<span style="font-size: 2em">Demo</span>
</div>

---

### Use Cases

<ul class=" ">
<li class="fragment  ">Fast checkout experience</li>
<li class="fragment  ">Consistent error handling</li>
<li class="fragment  ">Express checkout</li>
</ul>

Note:

- Fast checkout experience: Users can enter their details (credit cards and shipping addresses) once into the browser and are then ready to pay for goods and services on the web. They no longer have to fill out the same details repeatedly across different sites, thereby reducing shopping-cart abandonment.
- Consistent error handling: The browser can check the validity of card numbers, and can tell the user if a card has expired (or is about to expire). The browser can automatically suggest which card to use based on past usage patterns or restrictions from the merchant (e.g, "we only accept Visa or Mastercard"), or allow the user to say which is their default/favorite card.
- Express checkout: Let the customer buy without requiring to log in first. If you like, you can collect the user's contact details using the Payment Request UI and once they have made the purchase, offer the opportunity to create an account then, for future use.

---
<!-- .slide: data-background-image="./assets/md/assets/payment-request.png" data-background-size="90% auto" data-background-position="center" data-background=" " data-background-repeat=" " data-background-transition="none" -->


<div class="north">
<span style="font-size: 1.5em">Browser Support</span>
</div>

<div class="south">
https://caniuse.com/#feat=payment-request
</div>


---

## Recap

<ul class=" ">
<li class="fragment  ">A modern solution to handle scroll events (Intersection Observer API)</li>
<li class="fragment  ">Keep login simple for your users (Credential Management API)</li>
<li class="fragment  ">Make your website network-responsive (Network Information API)</li>
</ul>

---

## Recap

<ul class=" ">
<li class="fragment  ">Sharing made ridiculously easy (Web Share API)</li>
<li class="fragment  ">Tailor content dynamically based on device memory (Device Memory API)</li>
<li class="fragment  ">Buy seamlessly on the web (Payment Request API)</li>
</ul>

Note:
I'd like to add that all of these APIs can be used progressively, i.e. you can integrate them in your websites in such a way that users who are on supported browsers can be upgraded to a new experience while those who are still on unsupported browsers will remain on your old flow.
On that note, I'd just like to emphasize one last thing. Always develop features keeping your users in mind and not just for the sake of it.
That's all I have for today. Thank you for your time!

---
<!-- .slide: data-background="#020203" -->


<span style="font-size: 2em"><span style="color: #e49436">fin.</span></span>