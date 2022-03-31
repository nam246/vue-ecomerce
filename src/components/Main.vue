<template>
    <div class="main-content">
            <div class="product">
                <div>
                    <img  src="../assets/images/image-product-1.jpg" class="product-big">
                </div>
                <div class="product-thumbnail">
                    <div><img src="../assets/images/image-product-1-thumbnail.jpg" class="product-thumbnail-item"></div>
                    <div><img src="../assets/images/image-product-2-thumbnail.jpg" class="product-thumbnail-item"></div>
                    <div><img src="../assets/images/image-product-3-thumbnail.jpg" class="product-thumbnail-item"></div>
                    <div><img src="../assets/images/image-product-4-thumbnail.jpg" class="product-thumbnail-item"></div>
                </div>
            </div>

            <div class="product-detail">
                <div class="company-name">sneaker company</div>
                <div class="product-name">Fall Limited Edition Sneaker</div>
                <div class="product-description">
                    These low-profile sneakers are your perfect casual wear companion. Featuring a durable
                    rubber outer sole, they'll withstand everything the weather can offer.
                </div>

                <div class="product-price">
                    <div class="product-lastest-price">${{ product.price * product.discount / 100 }} <span class="product-discount">{{ product.discount }}%</span></div>
                    <div class="product-price-before">${{ product.price }}</div>
                </div>

                <div class="add-to-cart">
                    <div class="quantity">
                        <span><img src="../assets/images/icon-minus.svg" id="minus" 
                        @click="product.quantity > 0 ? product.quantity-- : product.quantity = 0"></span> 
                        <p id="qty">{{ product.quantity }}</p>
                        <span><img src="../assets/images/icon-plus.svg" id="plus" 
                        @click="product.quantity++"></span>
                    </div>
                    <div class="atc-btn" @click="$emit('add-to-cart')">
                        <img src="../assets/images/icon-cart.svg">Add to cart
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    name: 'Main',
    props: ['product'],
}
</script>

<style scoped>
.main-content {
    width: 80%;
    margin: 0 auto;
    padding-top: 2.4rem;
    display: flex;
    flex-direction: row;
    /* align-items: center; */
    justify-content: center;
}

.product {
    width: 50%;
}

.product-big {
    width: 24vw;
    border-radius: 8px;
}

.product-thumbnail {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: 24vw;
    padding-top: 12px;
}

.product-thumbnail-item {
    width: 5vw;
    border-radius: 5px;
}

.product-thumbnail-item:hover {
    border: 1.5px solid var(--orange);
    opacity: 0.7;
}

.product-detail {
    padding: 1.2rem 2.4rem;
    display: flex;
    flex-direction: column;
    width: 50%;
}

.company-name {
    color: var(--orange);
    font-weight: 700;
    margin-bottom: 1.2rem;
}

.product-name {
    font-size: 38px;
    font-weight: 700;
    margin-bottom: 1.4rem;
}

.product-description {
    font-size: 16px;
    color: var(--dark-grayish-blue);
    margin-bottom: 1.4rem;
}

.product-lastest-price {
    font-weight: 700;
    font-size: 24px;
    margin-bottom: 0.8rem;
}

.product-discount {
    background-color: var(--pale-orange);
    color: var(--orange);
    padding: 5px 5px;
    border-radius: 5px;
    font-weight: 700;
    margin-left: 0.8rem;
    font-size: 20px;
}

.product-price-before {
    color: var(--dark-grayish-blue);
    margin-bottom: 2.4rem;
    text-decoration-line: line-through;
}

.add-to-cart {
    display: flex;
    flex-direction: row;
    align-items: center;
    min-height: 77px;
}

.quantity {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    background-color: var(--light-grayish-blue);
    width: 40%;
    height: 50px;
    padding: 1rem 0.5rem;
    text-align: center;
    font-weight: 700;
    border-radius: 5px;
    box-shadow: 0px 2px 10px 2px var(--grayish-blue);
}

.quantity > span > img {
    cursor: pointer;
    display: block;
    padding: 15px 15px;
}

.quantity > input {
    width: 24px;
    height: 24px;
    text-align: center;
    padding: 1.2rem 1.2rem;
}

.atc-btn {
    font-size: 14px;
    font-weight: 700;
    color: var(--white);
    background-color: var(--orange);
    text-align: center;
    padding: 0.8rem 2.4rem;
    line-height: 24px;
    border-radius: 5px;
    margin-left: 0.8rem;
    cursor: pointer;
}
</style>