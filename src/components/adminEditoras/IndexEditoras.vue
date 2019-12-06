<template>
  <div>
    <div class="admin-new">
      <div class="container">
        <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
          <ul class="admin-menu">
            <!-- Links para as rotas irmãs -->
            <li>
              <router-link to="/adminEditoras/Editoras">Ver Editoras</router-link>
            </li>
            <li>
              <router-link to="/adminEditoras/NovaEditora">Nova Editora</router-link>
            </li>
          </ul>
        </div>
        <!-- Outlet para as rotas filhas -->
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>