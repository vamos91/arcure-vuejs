<template>
  <div id="nav">

    <ul id="navbar">
      <li>Username</li>
      <li>Logout</li>
      <li>Dashboard</li>
      <li>Admin contact</li>
    </ul>

  </div>
</template>

<script>
  export default{
    name: 'Navbar'
  }
</script>

<style scope>
#nav{
  background-color: white;
  color: gray;
  height: 7vh;
  display: flex;
  align-items: center;
  font-size: 14px;
  width: 100%;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);

}

#navbar{
  width: 30%;
  display: flex;
  list-style: none;
  justify-content: space-around;
  margin-left: 20px;
}

</style>
