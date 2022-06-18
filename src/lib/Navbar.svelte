<script lang="ts">
    let expand_navbar = false

    function toggle_navbar() {
        if(expand_navbar == false) {
            expand_navbar = true
        }else {
            expand_navbar = false
        }
    }
</script>

<nav>
    <button on:click={toggle_navbar} class="toggler {expand_navbar ? 'shown' : ''}">
        <span></span>
        <span></span>
        <span></span>
    </button>
    
    <div class="nav {expand_navbar ? 'shown' : ''}">
        <a on:click={toggle_navbar} sveltekit:prefetch href="/">Beranda</a>
        <a on:click={toggle_navbar} sveltekit:prefetch href="/cart">Keranjang Belanjaan</a>
        <a on:click={toggle_navbar} sveltekit:prefetch href="/kategori">Kategori</a>
        <a on:click={toggle_navbar} sveltekit:prefetch href="/tentang">Tentang Kami</a>
    </div>

    <a href="/cart" sveltekit:prefetch class="cart-button {expand_navbar ? 'shown' : ''}">
        cart
    </a>
</nav>

<style scoped lang="less">
    nav {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 4rem;
        background: #6777cc;
        display: flex;
        align-items: center;
        padding: 0 .5rem;
        z-index: 1000;

        .toggler {
            width: 50px;
            height: 50px;
            border: none;
            background: transparent;
            position: relative;
            outline: none;

            &.shown {
                span:nth-child(1) {
                    transform: translateX(-50%) rotate(45deg);
                    transition: 0.2s;
                    top: 25px;
                }
                span:nth-child(2) {
                    transition: 0.2s;
                    opacity: 0;
                }
                span:nth-child(3) {
                    transform: translateX(-50%) rotate(-45deg);
                    transition: 0.2s;
                    top: 25px;
                }
            }

            span {
                position: absolute;
                width: 65%;
                height: 3px;
                background: white;
                left: 50%;
                transform: translateX(-50%);
                transition: 0.2s;

                &:nth-child(1) {
                    top: 15px;
                }
                &:nth-child(2) {
                    top: 25px;
                }
                &:nth-child(2) {
                    top: 35px;
                }
            }
        }

        .nav {
            position: absolute;
            background: darken(white, 10%);
            top: 4rem;
            left: -75%;
            width: 75%;
            height: calc(100vh - 4rem);
            display: flex;
            flex-direction: column;
            transition: 0.2s;

            &.shown {
                left: 0;
            }

            a {
                padding: .75rem 1rem;
                text-decoration: none;
                color: #6777cc;
                transition: 0.2s;

                &:hover {
                    transition: 0.2s;
                    background: #6777cc;
                    color: white;
                }
            }
        }

        .cart-button {
            margin-left: auto;
            display: block;

            &.shown {
                display: none;
            }
        }
    }
</style>