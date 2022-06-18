<script lang="ts">
    const banner_item = [
        "https://picsum.photos/id/0/1200/800",
        "https://picsum.photos/id/1/1200/800",
        "https://picsum.photos/id/2/1200/800",
        "https://picsum.photos/id/237/1200/800",
    ]

    let active_banner = 0

    function move_left() {
        if(active_banner == 0) {
            active_banner = banner_item.length - 1
        }else {
            active_banner = active_banner - 1
        }
    }
    function move_right() {
        if(active_banner == banner_item.length - 1) {
            active_banner = 0
        }else {
            active_banner = active_banner + 1
        }
    }
</script>

<svelte:head>
    <title>Beranda</title>
</svelte:head>

<div class="carousel">
    <div class="item">
        <img preload={banner_item[active_banner]} src={banner_item[active_banner]} alt="Foto Banner">
    </div>
    <button class="left" on:click|preventDefault={move_left}>
        <span></span>
        <span></span>
    </button>
    <button class="right" on:click|preventDefault={move_right}>
        <span></span>
        <span></span>
    </button>
</div>

<div class="container">

</div>

<style lang="less">
    .container {
        width: 97%;
        margin: 0 auto;
    }

    .carousel {
        width: 100%;
        height: 13rem;
        overflow: hidden;
        position: relative;

        .item {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            min-width: 90%;
            height: 11rem;
            border-radius: 12px;
            overflow: hidden;
            display: flex;
            
            img {
                width: 100%;
                object-fit: cover;
            }
        }

        .left {
            position: absolute;
            top: 50%;
            left: 7%;
            transform: translateY(-50%);
            width: 30px;
            height: 30px;
            background: transparent;
            border: none;

            span {
                position: absolute;
                width: 12px;
                height: 2px;
                background: white;

                &:nth-child(1) {
                    top: 40%;
                    left: 50%;
                    transform: translate(-50%, -50%) rotate(-45deg);
                }
                &:nth-child(2) {
                    top: 65%;
                    left: 50%;
                    transform: translate(-50%, -50%) rotate(45deg);
                }
            }
        }

        .right {
            position: absolute;
            top: 50%;
            right: 7%;
            transform: translateY(-50%);
            width: 30px;
            height: 30px;
            background: transparent;
            border: none;

            span {
                position: absolute;
                width: 12px;
                height: 2px;
                background: white;

                &:nth-child(1) {
                    top: 40%;
                    left: 50%;
                    transform: translate(-50%, -50%) rotate(45deg);
                }
                &:nth-child(2) {
                    top: 65%;
                    left: 50%;
                    transform: translate(-50%, -50%) rotate(-45deg);
                }
            }
        }
    }
</style>
