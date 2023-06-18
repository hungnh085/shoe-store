<template>
  <div class="tw-grid tw-grid-cols-6 tw-content-center">
    <div class="tw-col-start-2 tw-col-span-4">
      <div class="tw-grid tw-grid-cols-2 tw-gap-4">
        <div>
          <q-carousel
            swipeable
            animated
            v-model="slide"
            thumbnails
            infinite
            class="tw-w-full tw-h-[600px]"
            v-if="choose === 'pink'"
          >
            <q-carousel-slide
              v-for="(item, index) in Data.image1"
              :key="index"
              :name="index"
              :img-src="item.src"
            />
          </q-carousel>
          <q-carousel
            swipeable
            animated
            v-model="slide"
            thumbnails
            infinite
            class="tw-w-full tw-h-[600px]"
            v-if="choose === 'black'"
          >
            <q-carousel-slide
              v-for="(item, index) in Data.image2"
              :key="index"
              :name="index"
              :img-src="item.src"
            />
          </q-carousel>
        </div>
        <div>
          <p class="tw-text-[#212529] tw-text-[28px] tw-mb-[8px]">
            {{ Data.name }} {{ Data.code }}
          </p>
          <div class="tw-flex tw-items-center tw-mb-[10px]">
            <p class="tw-text-[#212529] tw-text-[28px] tw-font-bold tw-mr-3">
              {{
                Intl.NumberFormat("en-VI", {
                  currency: "VND",
                }).format(Data.coat)
              }}₫
            </p>
            <p class="tw-text-[24px] tw-line-through">
              {{
                Intl.NumberFormat("en-VI", {
                  currency: "VND",
                }).format(Data.coatStock)
              }}₫
            </p>
          </div>
          <p class="tw-text-[15px] tw-text-[#212529] tw-mb-[10px]">Chọn màu:</p>
          <div class="tw-flex tw-mt-2">
            <img
              :src="Data.image1[0].src"
              alt=""
              class="tw-w-12 tw-mr-1 tw-cursor-pointer"
              :class="`${choose === 'pink' ? 'select-type' : ''}`"
              @click="
                {
                  choose = 'pink';
                  slide = 0;
                }
              "
            />
            <img
              :src="Data.image2[0].src"
              alt=""
              class="tw-w-12 tw-cursor-pointer"
              :class="`${choose === 'black' ? 'select-type' : ''}`"
              @click="
                {
                  choose = 'black';
                  slide = 0;
                }
              "
            />
          </div>
          <p class="tw-text-[15px] tw-text-[#212529] tw-mt-4 tw-mb-[10px]">
            Chọn size:
          </p>
          <div class="tw-flex tw-mt-2">
            <p
              v-for="(item, index) in Data.size"
              :key="index"
              class="size tw-cursor-pointer"
              :class="`${formData.size === item ? 'select-type' : ''}`"
              @click="formData.size = item"
            >
              {{ item }}
            </p>
          </div>
          <p class="tw-text-[15px] tw-text-[#212529] tw-mt-4 tw-mb-[10px]">
            Số lượng:
          </p>
          <div class="tw-flex tw-mt-2 quantity">
            <p class="tw-cursor-pointer" @click="reduce">-</p>
            <p>{{ formData.count }}</p>
            <p class="tw-cursor-pointer" @click="formData.count++">+</p>
          </div>
          <div class="tw-text-center form-order tw-mt-4">
            <p class="tw-mb-2 tw-text-[16px] tw-text-[#212529] tw-font-bold">
              THÔNG TIN ĐẶT HÀNG
            </p>
            <div class="tw-grid tw-grid-cols-2 tw-gap-2">
              <q-input
                outlined
                dense
                placeholder="Số điện thoại"
                v-model="formData.phone"
              />
              <q-input
                outlined
                dense
                placeholder="Họ và tên"
                v-model="formData.name"
              />
            </div>
            <q-input
              outlined
              dense
              placeholder="Địa chỉ nhận hàng"
              class="tw-mt-2"
              v-model="formData.address"
            />
            <q-btn
              unelevated
              color="red"
              class="tw-w-[225px] tw-mt-2"
              @click="submit"
              >Đặt Hàng</q-btn
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
const slide = ref(1);
const choose = ref("pink");
const changeText = () => {
  if (slide.value === 4) {
    slide.value = 0;
  }
  setTimeout(() => {
    slide.value = slide.value + 1;
    changeText();
  }, 3500);
};
const formData = ref({
  code: "",
  color: "",
  size: 36,
  count: 1,
  phone: "",
  name: "",
  address: "",
});
const Data = ref({
  name: "Giày Lười Vải Nữ",
  code: "AG0142",
  coat: "249000",
  coatStock: "389000",
  size: [36, 37, 38, 39],
  image1: [
    {
      id: 1,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-7.jpg",
    },
    {
      id: 2,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-7.jpg",
    },
    {
      id: 3,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-7.jpg",
    },
    {
      id: 4,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-7.jpg",
    },
  ],
  image2: [
    {
      id: 5,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-1.jpg",
    },
    {
      id: 6,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-1-1.jpg",
    },
    {
      id: 7,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-1.jpg",
    },
    {
      id: 8,
      src: "https://agiay.vn/wp-content/uploads/2022/04/giay-luoi-vai-nu-ag0142-1-1.jpg",
    },
  ],
});
const reduce = () => {
  if (formData.value.count != 1) {
    formData.value.count--;
  }
};
const submit = () => {
  formData.value.code = Data.value.code;
  formData.value.color = choose.value;
  console.log("Data: ", formData.value);
};
onMounted(() => {
  changeText();
});
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
.select-type {
  border: 2px solid black !important;
  padding: 1px;
}
.size {
  border: 2px solid #ccc;
  padding: 6px 10px;
  height: 40px;
  width: 40px;
  line-height: 23px;
  font-size: 14px;
  text-align: center;
  margin-right: 4px;
}
.quantity > p {
  padding: 7px 10px 8px;
  height: 39px;
  border: 1px solid #efefef;
}
.form-order {
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 7px;
}
</style>
