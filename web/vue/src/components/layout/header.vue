<template lang='jade'>
  div
    #top
    nav
      .menu.contain
        router-link(to='/home').py1 BOT
        router-link(to='/live-gekkos').py1 Live Bots
        router-link(to='/backtest').py1 Backtest
        router-link(to='/data').py1 Local data
        router-link(to='/config').py1 Config

</template>

<script>
export default {}
</script>

<style>
.menu {
  display: flex;
  width: 100%;
  flex-direction: row;
  margin-top: 0;
  margin-bottom: 2rem;
}

.menu a {
  flex: 1 1 100%;
  display: block;
  text-align: center;
  text-decoration: none;
  color: #FFC300  ;

}

.menu .router-link-active {
  background-color: rgba(250,250,250,.99);
  color:#000;
}

.menu a:hover {
  text-decoration: none;
  background-color:#FFC300;
  color: #000;
}
.menu .router-link-active {
  text-decoration: none;
  background-color:#FFC300;
}
h1{
  padding-right: 20px;
}
nav{
  background-color:#000;
}
</style>
