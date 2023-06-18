<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <div
        class="tw-flex tw-bg-[#0E1D49] tw-h-[31px] tw-items-center tw-justify-center"
      >
        Miễn phí ship toàn quốc cho đơn hàng từ 299,000đ
      </div>
      <div
        class="tw-grid tw-grid-cols-6 tw-h-20 tw-content-center tw-border-b-2 tw-shadow-md tw-bg-white"
      >
        <div class="tw-col-start-2 tw-col-span-4">
          <div class="tw-grid tw-grid-cols-3">
            <div class="tw-flex tw-items-center tw-justify-center">
              <p
                class="tw-mr-3 tw-cursor-pointer tw-text-[15px] tw-text-black"
                @click="router.push('/men-shoe')"
              >
                GIÀY NAM
              </p>
              <p class="tw-cursor-pointer tw-text-[15px] tw-text-black">
                GIÀY NỮ
              </p>
            </div>
            <div class="tw-flex tw-items-center tw-justify-center">
              <img
                src="../assets/logo.png"
                alt=""
                class="tw-h-[40px] tw-cursor-pointer"
                @click="router.push('/')"
              />
            </div>
            <div class="tw-flex tw-items-center tw-justify-center">
              <q-icon
                size="sm"
                class="tw-mr-3 tw-cursor-pointer"
                name="search"
                color="black"
              />
              <q-icon
                size="sm"
                class="tw-mr-3 tw-cursor-pointer"
                name="person"
                color="black"
              />
              <q-icon
                size="sm"
                class="tw-mr-3 tw-cursor-pointer"
                name="call"
                color="black"
              />
              <q-icon
                size="sm"
                class="tw-cursor-pointer"
                name="shopping_cart"
                color="black"
              />
            </div>
          </div>
        </div>
      </div>
    </q-header>
    <q-page-container class="tw-mt-4">
      <q-page class="tw-flex">
        <q-scroll-area
          class="tw-grow"
          :thumb-style="thumbStyle"
          :bar-style="barStyle"
        >
          <router-view />
          <div
            class="tw-grid tw-grid-cols-6 tw-mt-8 tw-content-center tw-bg-[#efefef] tw-py-8"
          >
            <div class="tw-col-start-2 tw-col-span-4">
              <div class="tw-grid tw-grid-cols-3">
                <div class="tw-px-[12px]">
                  <p class="tw-font-medium tw-text-[18px]">THS.VN</p>
                  <div
                    class="tw-flex tw-items-center tw-mt-2 tw-cursor-pointer"
                    @click="gotoStore"
                  >
                    <q-icon
                      size="sm"
                      color="red-9"
                      name="location_on"
                      class="tw-mr-2"
                    />
                    <p>Thôn Phú Xuyên 4, xã Phú Châu, Huyện Ba Vì, Hà Nội</p>
                  </div>
                  <div
                    class="tw-flex tw-items-center tw-mt-1 tw-cursor-pointer"
                  >
                    <q-icon
                      size="sm"
                      color="blue-3"
                      name="add_to_home_screen"
                      class="tw-mr-2"
                    />
                    <p>Tư vấn mua hàng: 098.122.2070</p>
                  </div>
                  <div
                    class="tw-flex tw-items-center tw-mt-1 tw-cursor-pointer"
                  >
                    <q-icon
                      size="sm"
                      color="blue-3"
                      name="add_to_home_screen"
                      class="tw-mr-2"
                    />
                    <p>Liên hệ ZALO: 098.122.2070</p>
                  </div>
                  <div
                    class="tw-flex tw-items-center tw-mt-1 tw-cursor-pointer"
                  >
                    <q-icon
                      size="sm"
                      color="blue-3"
                      name="add_to_home_screen"
                      class="tw-mr-2"
                    />
                    <p>Hỗ trợ giờ hành chính: 9h - 17h (Thứ 2 tới Thứ 7)</p>
                  </div>
                  <div
                    class="tw-flex tw-items-center tw-mt-1 tw-cursor-pointer"
                  >
                    <q-icon
                      size="sm"
                      color="amber-5"
                      name="outgoing_mail"
                      class="tw-mr-2"
                    />
                    <p>Email: ths.vn@gmail.com</p>
                  </div>
                </div>
                <div class="tw-px-[12px]">
                  <p class="tw-font-medium tw-text-[18px]">
                    HƯỚNG DẪN & CHÍNH SÁCH
                  </p>
                  <div class="tw-mt-2">
                    <p class="tw-cursor-pointer">Tin Tức</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Liên Hệ</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Giới Thiệu</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Hướng Dẫn Mua Hàng</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Chính Sách bảo Hành</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Giao Nhận Thanh Toán</p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">Chính Sách Bảo Mật</p>
                  </div>
                </div>
                <div class="tw-px-[12px]">
                  <p class="tw-font-medium tw-text-[18px]">
                    CÔNG TY TNHH THS.COM
                  </p>
                  <div class="tw-mt-2">
                    <p class="tw-cursor-pointer">
                      MST: 0109644965, cấp ngày 24/05/2021
                    </p>
                  </div>
                  <div class="tw-mt-1">
                    <p class="tw-cursor-pointer">
                      Sở kế hoạch & đầu tư thành phố Hà Nội
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </q-scroll-area>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { useRouter } from "vue-router";
const router = useRouter();
const thumbStyle = {
  right: "4px",
  borderRadius: "5px",
  backgroundColor: "#027be3",
  width: "5px",
  opacity: 0.75,
};

const barStyle = {
  right: "2px",
  borderRadius: "9px",
  backgroundColor: "#027be3",
  width: "9px",
  opacity: 0.2,
};

const gotoStore = () => {
  window.open("https://goo.gl/maps/qiWGjxgBr5DnCHf59");
};
</script>
