<template>
    <div class="wrapper">
        <div v-for="perfume in perfumes" class="perfume">
            <div class="exclusive-btn">EXCLUSIVE</div>
            <div class="favorite"><img src="../assets/images/heart.svg" width='20px' alt=""></div>
             <!-- name, price, discount, description, image -->
            <div class="image"><img :src="perfume.image_url" width="100%" alt=""></div>
            <div class="description-container">
                <div class="coupon">Save 10% - Use Code: EID</div>
                <div class="name line-clamp-name">{{perfume.name}}</div>
                <div class="description line-clamp" :title="perfume.description" v-html="perfume.description"></div>
                <div class="pricing-container">
                    <div class="price">{{perfume.price.SAR.default_formated}}</div>
                    <div class="discount">-20%</div>
                </div>
                <div class="pricing-container">
                    <div class="save-price">{{perfume.price.SAR.default_formated + 30}}</div>
                    <div class="save">Save SAR 30</div>
                </div>
            </div>    
        </div>
    </div>
</template>

<script>
export default {
 name: 'Perfume',
 props:['perfumes'],
 data(){
     return {
     }
 },
 methods:{
    
 }
}
</script>
<style scoped>
   .pricing-container{
       display:flex;
       justify-content: space-between;
       width:100%;
       padding:10px 0px;
       align-items: center;
   }
   .perfume{
       position:relative;
       margin:10px;
       background:white;
       padding:25px;
       font-size:12px;
   }
   .wrapper {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
   }
    @media only screen and (max-width: 600px) {
        .wrapper {
            display: grid;
            grid-template-columns: repeat(1, 1fr);
        }
    }
   .line-clamp {
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;  
    overflow: hidden;
    }
   .line-clamp-name {
    display: -webkit-box;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;  
    overflow: hidden;
    }
    .name{
        font-weight: bold;
    }
    .price{
        color:red;
        font-weight: 800;
    }
    .discount{
        border-radius: 4px;
        padding: 3px;
        font-size: 11px;
        background: #baf3ba;
        font-weight:600;
    }
    .description{
        color:#a19f9f
    }
    p{
        margin:0px;
    }
    .save{
        font-weight: bold;
    }
    .save-price{
        text-decoration: line-through;
        color:#a19f9f
    }
    .exclusive-btn{
        position:absolute;
        left:10px;
        top:10px;
        font-weight: bold;
        border:2px solid black;
        border-radius:30px;
        padding:2px 5px;
    }
    .favorite{
        position:absolute;
        top:8px;
        right:10px;
    }
    .description-container{
        position: relative;
        margin-top: 40px;
    }
    .coupon{
        position:absolute;
        left:0px;
        top:-35px;
        font-weight: bold;
        border:2px solid rgb(144, 143, 199);
        background:rgb(216, 213, 231);
        border-radius:30px;
        padding:2px 5px;
    }
   
</style>
