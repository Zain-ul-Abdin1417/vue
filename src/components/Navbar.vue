<template>
    <nav class="navbar">
        <div class="nav-bar">
            <ul class="nav-">
            <div class="brand-logo">
                <a href="https://zain.alphasofthub.com/" class="brand-link" target="_blank"><h1 class="brand">{{ brand }}</h1></a>
            </div>
                <li><a><router-link to="/home">Home</router-link></a></li>
                <li><a><router-link>Converter</router-link></a></li>
                <li><a><router-link>Calculator</router-link></a></li>
                <li><a><router-link>About</router-link></a></li>
            
            </ul>
        </div>
    </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    title: String
  },
  data: function () {
    return {
      brand: 'ZUA'
    }
  },
}
</script>

<style scoped>

.nav-bar {
    width: 100%;
    background-color: rgb(33, 165, 241);
    height: 20%;
    display: flex;
    /* padding: 10px; */
}
ul {
    display: flex;
    /* padding-left: 10px; */
}

li {
    /* cursor: ; */
    padding-left: 15%;
    padding-top: 5%;
    padding-bottom: 8%;
    list-style: none;
}

.nav-bar h1{
    align-content: baseline;
}

.brand-logo {
    width: 15%;
    height: 5%;
    /* margin-right: 5%; */
    margin-top: 4%;
    padding-left: 10px;
}

a {
    text-decoration: none;
    color: black;
}

a:hover {
    color: white;
}

li:hover {
    color: white;
    font-size: 16px;
}

router-link {
    cursor: pointer;
}
</style>