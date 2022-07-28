<template>
    <b-navbar toggleable="sm" type="dark" variant="dark" class="px-3">
        <b-navbar-brand href="/">Crosswood</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ms-auto">
                
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
</template>
<script>
export default {
    name: 'HeaderComponent',
    props: {
        msg: String
    }
}
</script>