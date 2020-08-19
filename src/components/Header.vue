<template>
  <!-- Header -->
  <header class="header-section">
    <div class="container">
      <div class="inner-header" style="margin-top: -3vh">
        <div class="row">
          <div class="col-lg-2 col-md-2">
            <div class="logo">
              <a href="/">
                <img src="img/q3@2x.png" />
              </a>
            </div>
          </div>
          <div class="col-lg-7 col-md-7"></div>
          <div class="col-lg-3 text-right col-md-3">
            <ul class="nav-right">
              <li class="cart-icon">
                Lihat Belanja &nbsp;
                <a href="#">
                  <i class="icon_bag_alt"></i>
                  <span>{{ keranjangUser.length }}</span>
                </a>
                <div class="cart-hover">
                  <div class="select-items">
                    <table>
                      <tbody v-if="keranjangUser.length > 0">
                        <tr v-for="keranjang in keranjangUser" :key="keranjang.id">
                          <td class="si-pic">
                            <img class="photo-item" :src="keranjang.photo" alt />
                          </td>
                          <td class="si-text">
                            <div class="product-selected">
                              <h6>{{ keranjang.name }}</h6>
                              <p>Rp {{ keranjang.price }}.000</p>
                            </div>
                          </td>
                          <td @click="removeItem(keranjang.id)" class="si-close">
                            <i class="ti-close"></i>
                          </td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                  <div class="select-total">
                    <span>total Belanja:</span>
                    <h5>Rp {{ totalHarga }}.000</h5>
                  </div>
                  <div class="select-button">
                    <a href="#" class="primary-btn view-card">
                      <router-link to="/cart" style="color: #ffffff;">VIEW CARD</router-link>
                    </a>
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </header>
  <!-- Header End -->
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      keranjangUser: []
    };
  },
  methods: {
    removeItem(idx) {
      // Cari tahu id dari si item yang akan dihapus
      let keranjangUserStorage = JSON.parse(
        localStorage.getItem("keranjangUser")
      );
      let itemKeranjangUserStorage = keranjangUserStorage.map(
        itemKeranjangUserStorage => itemKeranjangUserStorage.id
      );

      // Mencocokan id item dengan id yang ada di storage
      let index = itemKeranjangUserStorage.findIndex(id => id == idx);
      this.keranjangUser.splice(index, 1);

      const parsed = JSON.stringify(this.keranjangUser);
      localStorage.setItem("keranjangUser", parsed);
      window.location.reload();
    }
  },
  mounted() {
    if (localStorage.getItem("keranjangUser")) {
      try {
        this.keranjangUser = JSON.parse(localStorage.getItem("keranjangUser"));
      } catch (e) {
        localStorage.removeItem("keranjangUser");
      }
    }
  },
  computed: {
    totalHarga() {
      return this.keranjangUser.reduce(function(items, data) {
        return parseFloat(items) + parseFloat(data.price);
      }, 0);
    }
  }
};
</script>

<style scoped>
.photo-item {
  width: 80px;
  height: 80px;
}
</style>
