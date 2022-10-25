<template>
    <footer class="footer">
        <div class="footer__inner footer--border-top-gray">
            <small class="footer-copyright">
                © Masayuki Tamura
            </small>
        </div>
    </footer>
</template>
  
<script>
  
export default {
    name: 'MyFooter',
    components: {}
}
</script>

<style>
.footer {
    padding-top: 20px;
    padding-bottom: 20px;
    /* background-color: #222; */
}
.footer--border-top-gray {
    border-top: 1px solid #777;
}
.header__inner {
    max-width: 1230px;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
}
</style>
