<template>
  <MobileMenu/>
  <AppHeader/>
  <NuxtPage data-aos="fade-in"/>
  <AppFooter/>
</template>

<script>
import AOS from 'aos';
import 'aos/dist/aos.css'; // You can also use <link> for styles
import { initializeApp } from "firebase/app";

const firebaseConfig = {
  apiKey: "AIzaSyCrSdb4HDzcj-f1UZ5xR4BDw9_eMl2wHGg",
  authDomain: "tarunguptaraja-44b14.firebaseapp.com",
  projectId: "tarunguptaraja-44b14",
  storageBucket: "tarunguptaraja-44b14.appspot.com",
  messagingSenderId: "670070076193",
  appId: "1:670070076193:web:f58f454718dcc9cce68460",
  measurementId: "G-F8T4ECDYLX"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);


export default {
  /**
   * * Watch for route changes
   * This event is triggered when the route changes.
   * @param {Object} to - Route object
   * @param {Object} from - Route object
   */
  watch: {
    $route(to, from) {
      console.log('De', from.fullPath, 'a', to.fullPath);
    }
  },
  mounted() {
    AOS.init({
        // Global settings:
        disable: false, // accepts following values: 'phone', 'tablet', 'mobile', boolean, expression or function
        startEvent: 'DOMContentLoaded', // name of the event dispatched on the document, that AOS should initialize on
        initClassName: 'aos-init', // class applied after initialization
        animatedClassName: 'aos-animate', // class applied on animation
        useClassNames: false, // if true, will add content of `data-aos` as classes on scroll
        disableMutationObserver: false, // disables automatic mutations' detections (advanced)
        debounceDelay: 50, // the delay on debounce used while resizing window (advanced)
        throttleDelay: 99, // the delay on throttle used while scrolling the page (advanced)
        
        // Settings that can be overridden on per-element basis, by `data-aos-*` attributes:
        offset: 120, // offset (in px) from the original trigger point
        delay: 0, // values from 0 to 3000, with step 50ms
        duration: 400, // values from 0 to 3000, with step 50ms
        easing: 'ease', // default easing for AOS animations
        once: false, // whether animation should happen only once - while scrolling down
        mirror: false, // whether elements should animate out while scrolling past them
        anchorPlacement: 'top-bottom', // defines which position of the element regarding to window should trigger the animation
    });
  }
}
</script>