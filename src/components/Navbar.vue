<template>
    <nav :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar' , 'navbar-expand-lg']">
                    <div class="container-fluid">
                        <a class="navbar-brand" href="#">Navbar</a>
                        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                            aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                            <span class="navbar-toggler-icon"></span>
                        </button>
                        <div class="collapse navbar-collapse" id="navbarNav">
                            <ul class="navbar-nav">
                                <!-- Kenapa v-for="link dari links" ada disini? dikarenakan sifat vue sendiri menginginkan kita untuk memahami Code kita -->
                                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                                    <a class="nav-link" aria-current="page" :class="{ active: activePage == index }"
                                        :title="`This link goes to ${page.link.text}`" @click.prevent="navLinkClick(index)"
                                        v-bind:href="page.link.url">{{ index }}
                                        {{ page.link.text }}</a>
                                </li>
                            </ul>
                        </div>
                        <form class="d-flex" action="">
                            <button class="btn btn-primary" @click.prevent="changeTheme()">dark</button>
                        </form>
                    </div>
                </nav>
</template>

<script>
export default{
     props: ['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'light',
        }
    },
    methods: {
        changeTheme() {
            let theme = 'light';
            if (this.theme == 'light') {
                theme = "dark";
            }

            this.theme = theme
        }
    }
}
</script>