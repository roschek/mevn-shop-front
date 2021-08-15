<template>
    <header class=header>
        <div class="header_left">LOGO</div>
        <div class="header_right">
            <ul class="nav">
                <li class="nav_link" 
                v-for="(category, idx) in categories" 
                :key="idx">
                    <router-link :to="`category/${category.id}`" class="link">{{category.title}}</router-link>
                </li>
            </ul>
        </div>
    </header>
</template>

<script>
export default {
    name: 'MevnHeader',
    props: {
        categories: {
            type : Array,
            default: () => []
            }
        }
}
</script>

<style scoped>
    .header{
        display:flex;
        border-bottom: 1px solid grey;
        padding: 10px;
         justify-content: space-between;
         align-items: center;
    }
    .nav{
     list-style: none;
     display: flex;
     flex-direction: row;
    }
    .nav_link{
       margin-right: 40px; 
       cursor: pointer;      
       transition: .3s;
       padding-bottom:5px;
    }    
    .link:hover{
      color:blue;      
    }
</style>