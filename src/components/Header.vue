<template>
    <div class="header">
            <div class="header-left">
                <div class="logo"><img src="../assets/images/logo.svg"></div>
                <div class="menus">
                    <div class="menu-item">Collection</div>
                    <div class="menu-item">Men</div>
                    <div class="menu-item">Women</div>
                    <div class="menu-item">About</div>
                    <div class="menu-item">Contact</div>
                </div>
            </div>

            <div class="header-right">
                <img src="../assets/images/icon-cart.svg" class="cart" @click="showCartDetail">
                <div class="cart-detail" v-if="cartDetailHidden">
                    <div class="cart-detail-header">Cart</div>
                    <hr>
                    <div class="cart-detail-body" v-if="product.quantity == 0">
                        Your cart is empty
                    </div>
                    <div class="cart-detail-body" v-if="product.quantity > 0">
                        {{ product.name }} {{ product.quantity }}
                    </div>
                </div>
                <div class="user"><img src="../assets/images/image-avatar.png"></div>
            </div>
        </div>
</template>

<script>
import Main from './Main.vue'
export default {
    name: 'Header',
    props: [
        'product', 
        'cart',
        ],
    data() {
        return {
            cartDetailHidden: false,
        }
    },
    methods: {
        showCartDetail() {
            this.cartDetailHidden = !this.cartDetailHidden
        },
    },
    components: {
        Main,
    }
}
</script>

<style scoped>
.header {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 2.4rem;
}

.header-left {
    display: flex;
    flex-direction: row;
    align-items: center;
}

.menus {
    display: flex;
    flex-direction: row;
    align-items: center;
    color: var(--dark-grayish-blue);
    margin-left: 1.2rem;
}

.menu-item {
    margin-left: 1.2rem;
    padding: 1.2rem 1.2rem;
    cursor: pointer;
}

.menu-item:hover {
    color: var(--black);
}


.header-right {
    display: flex;
    flex-direction: row;
    align-items: center;
    position: relative;
}

.cart {
    cursor: pointer;
}

.cart:hover {
    font-weight: 700;
}

.cart-detail {
    position: absolute;
    background-color: #fff;
    min-width: 24vw;
    min-height: 34vh;
    right: 0;
    top: 74px;
    border-radius: 8px;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.25);
    border: 1px solid #000;
}

.cart-detail > .cart-detail-header {
    padding: 1.2rem 1.2rem;
    font-weight: 700;
}

.cart-detail > .cart-detail-body {
    padding: 1.2rem 1.2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    color: var(--dark-grayish-blue);
}

.user > img {
    width: 3.4rem;
    cursor: pointer;
    margin-left: 1.2rem;
}

.user > img:hover {
    border: 1.5px solid var(--orange);
    border-radius: 100%;
}
</style>