<template>
     <navbar :pages="pages" :active-page="activePage" :nav-link-click="(index) => activePage = index"></navbar>

        <page-viewer class="container" :page="pages[activePage]">

        </page-viewer>
        
</template>

<script>

import pageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';

export default{
    components: {
        Navbar,
        pageViewer
    },
     data() {
        return {
            activePage: 0,
            pages: [{
                link: {
                    text: 'Home',
                    url: 'index.html'
                },
                pageTitle: 'Home Page',
                content: 'This is the Home Content'
            },
            {
                link: {
                    text: 'About',
                    url: 'about.html'
                },
                pageTitle: 'About Page',
                content: 'This is the About Content'
            },
            {
                link: {
                    text: 'Contact',
                    url: 'contact.html'
                },
                pageTitle: 'Contact Page',
                content: 'This is the Contact Content'
            },

            ]

        };
    }
}</script>