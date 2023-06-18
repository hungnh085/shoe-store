<template>
  <div class="tw-grid tw-grid-cols-6 tw-content-center">
    <div class="tw-col-start-2 tw-col-span-4">
      <div>
        <q-carousel
          v-model="slide"
          transition-prev="slide-right"
          transition-next="slide-left"
          swipeable
          animated
          control-color="black"
          arrows
          height="300px"
          class="bg-grey-1 shadow-2 rounded-borders p-0"
        >
          <q-carousel-slide :name="1" class="column no-wrap">
            <div class="fit justify-start items-center">
              <q-img
                class="rounded-borders col-6 full-height"
                src="../assets/image/1.jpg"
              />
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="2" class="column no-wrap">
            <div class="fit justify-start items-center">
              <q-img
                class="rounded-borders col-6 full-height"
                src="../assets/image/2.jpg"
              />
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="3" class="column no-wrap">
            <div class="fit justify-start items-center">
              <q-img
                class="rounded-borders col-6 full-height"
                src="../assets/image/3.jpg"
              />
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="4" class="column no-wrap">
            <div class="fit justify-start items-center">
              <q-img
                class="rounded-borders col-6 full-height"
                src="../assets/image/4.jpg"
              />
            </div>
          </q-carousel-slide>
        </q-carousel>
      </div>
      <h1 class="tw-text-[24px] tw-text-center">SẢN PHẨM MỚI</h1>
      <div
        class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
      >
        <q-card
          class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
          v-for="index in 10"
          :key="index"
          @click="router.push(`/${index}`)"
        >
          <img
            src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
          />

          <q-card-section class="tw-p-2">
            <div class="tw-text-[16px]">Giày Lười Da Bò Nam</div>
            <div class="text-subtitle2 tw-text-[20px]">
              {{
                Intl.NumberFormat("en-VI", {
                  currency: "VND",
                }).format("999000")
              }}đ
            </div>
          </q-card-section>

          <q-card-section class="q-pt-none tw-flex tw-p-3 tw-pt-0">
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12 tw-h-12 tw-mr-2 sub-img"
            />
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12"
            />
          </q-card-section>
        </q-card>
      </div>
      <h1 class="tw-text-[24px] tw-text-center tw-mt-4">GIÀY NAM</h1>
      <div
        class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
      >
        <q-card
          class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
          v-for="index in 10"
          :key="index"
          @click="router.push(`/${index}`)"
        >
          <img
            src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
          />

          <q-card-section class="tw-p-2">
            <div class="tw-text-[16px]">Giày Lười Da Bò Nam</div>
            <div class="text-subtitle2 tw-text-[20px]">
              {{
                Intl.NumberFormat("en-VI", {
                  currency: "VND",
                }).format("999000")
              }}đ
            </div>
          </q-card-section>

          <q-card-section class="q-pt-none tw-flex tw-p-3 tw-pt-0">
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12 tw-h-12 tw-mr-2 sub-img"
            />
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12"
            />
          </q-card-section>
        </q-card>
      </div>
      <div class="tw-flex tw-items-center tw-justify-center tw-mt-8">
        <q-btn
          unelevated
          icon-right="arrow_forward"
          label="xem thêm"
          class="btn-more tw-font-light tw-text-center tw-bg-[#efefef] tw-text-[#4a4a4a] tw-tracking-widest hover:tw-text-blue-400 tw-font"
          @click="router.push(`/men-shoe`)"
        />
      </div>
      <h1 class="tw-text-[24px] tw-text-center tw-mt-4">GIÀY NỮ</h1>
      <div
        class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
      >
        <q-card
          class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
          v-for="index in 10"
          :key="index"
          @click="router.push(`/${index}`)"
        >
          <div>
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
            />
          </div>

          <q-card-section class="tw-p-2">
            <div class="tw-text-[16px]">Giày Lười Da Bò Nam</div>
            <div class="text-subtitle2 tw-text-[20px]">
              {{
                Intl.NumberFormat("en-VI", {
                  currency: "VND",
                }).format("999000")
              }}đ
            </div>
          </q-card-section>

          <q-card-section class="q-pt-none tw-flex tw-p-3 tw-pt-0">
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12 tw-h-12 tw-mr-2 sub-img"
            />
            <img
              src="https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg"
              class="tw-w-12"
            />
          </q-card-section>
        </q-card>
      </div>
      <div class="tw-flex tw-items-center tw-justify-center tw-mt-8">
        <q-btn
          unelevated
          icon-right="arrow_forward"
          label="xem thêm"
          class="btn-more tw-font-light tw-text-center tw-bg-[#efefef] tw-text-[#4a4a4a] tw-tracking-widest hover:tw-text-blue-400 tw-font"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const slide = ref(1);
const listImg = [
  {
    id: 1,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 2,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 3,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 4,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 5,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 6,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },

  {
    id: 7,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
  },
];
</script>
<style lang="css" scoped>
.example-item {
  height: 290px;
  width: 290px;
}
.q-carousel__slide {
  padding: 0px !important;
}
.sub-img {
  border: 1.5px solid black;
  padding: 2px;
}
.btn-more .q-icon {
  font-size: 8px !important;
}
</style>
