<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-3 col-lg-2">
        <Sidebar />
      </div>
      <div class="col-md-9 ms-sm-auto col-lg-10 px-md-4">
        <div class="row">
          <div class="col">
            <Header/>
          </div>
          <div class="col-12">
            <Content/>
          </div>
        </div>
      </div>
    </div>
    <p></p>
  </div>
</template>

<script>
import Sidebar from "@/components/Head/Sidebar.vue";
import Header from "@/components/Head/Header.vue";
import Content from "@/views/Content.vue";
export default {
  name: "Home",
  components: {
    Sidebar,
    Header,
    Content,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
body{
  font-family:'Montserrat' !important;
}
h3{
  font-weight: bold;
  text-transform:uppercase;
  font-size:1.2em !important;
  color:#777;
  text-align: center;
}
.page-item.active .page-link{
  backgroud-color:rgb(132,94,167) !important
}
.card-text li{
  color:#777
}
b, strong{
  font-weight:bold;
  color:rgb(132,94,167)
}
</style>
