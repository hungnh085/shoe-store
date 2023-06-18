<template>
  <div class="tw-grid tw-grid-cols-6 tw-content-center">
    <div class="tw-ml-4">
      <p class="tw-text-[20px] tw-mb-2 tw-font-medium tw-mt-8">Danh mục</p>
      <p
        class="tw-cursor-pointer hover:tw-text-[#123a61]"
        :class="`${type === 1 ? 'tw-font-bold' : ''}`"
        @click="type = 1"
      >
        🌟 Giảm Giá Cực Sốc Đầu Xuân 🌟
      </p>
      <p
        class="tw-cursor-pointer hover:tw-text-[#123a61]"
        :class="`${type === 2 ? 'tw-font-bold' : ''}`"
        @click="type = 2"
      >
        Giày Công Sở Nam
      </p>
      <p
        class="tw-cursor-pointer hover:tw-text-[#123a61]"
        :class="`${type === 3 ? 'tw-font-bold' : ''}`"
        @click="type = 3"
      >
        Giày Da Nam
      </p>
      <p
        class="tw-cursor-pointer hover:tw-text-[#123a61]"
        :class="`${type === 4 ? 'tw-font-bold' : ''}`"
        @click="type = 4"
      >
        Giày Lười Nam
      </p>
      <p
        class="tw-cursor-pointer hover:tw-text-[#123a61]"
        :class="`${type === 5 ? 'tw-font-bold' : ''}`"
        @click="type = 5"
      >
        Giày Thể Thao Nam
      </p>
      <div class="tw-mt-4">
        <p class="tw-text-[20px] tw-mb-2 tw-font-medium">Khoảng Giá</p>
        <div class="row justify-around tw-pr-4">
          <q-range
            v-model="standard"
            :min="200000"
            :max="500000"
            color="grey"
            snap
            label-always
            switch-label-side
            @change="research"
          />
        </div>
      </div>
    </div>
    <div class="tw-col-start-2 tw-col-span-4">
      <!-- giam gia dau xuan -->
      <div v-if="type === 1">
        <p class="tw-text-[24px] tw-text-center tw-mt-8 tw-mb-4">
          🌟 Giảm Giá Cực Sốc Đầu Xuân 🌟
        </p>
        <div
          class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
        >
          <q-card
            class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
            v-for="item in data"
            :key="item.id"
            @click="router.push(`/${item.id}`)"
          >
            <div class="tw-flex tw-relative">
              <img :src="item.src" />
              <q-badge
                color="negative"
                class="tw-absolute tw-top-2 tw-right-2 tw-text-[14px] tw-px-3 tw-py-[2px] tw-rounded-none w-min-w-[70px]"
                v-if="item.coatStock"
                >{{
                  Math.round(100 - (item.coat / item.coatStock) * 100)
                }}
                %</q-badge
              >
            </div>

            <q-card-section class="tw-p-2">
              <div class="tw-text-[16px]">{{ item.name }}</div>
              <div class="text-subtitle2 tw-text-[20px] tw-flex">
                <p class="tw-font-bold tw-mr-3">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coat)
                  }}₫
                </p>
                <p class="tw-text-[18px] tw-line-through" v-if="item.coatStock">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coatStock)
                  }}₫
                </p>
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
      </div>
      <!-- end giam gia dau xuan -->
      <!-- giay cong so nam -->
      <div v-if="type === 2">
        <p class="tw-text-[24px] tw-text-center tw-mt-8 tw-mb-4">
          Giày Công Sở Nam
        </p>
        <div
          class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
        >
          <q-card
            class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
            v-for="item in data"
            :key="item.id"
            @click="router.push(`/${item.id}`)"
          >
            <div class="tw-flex tw-relative">
              <img :src="item.src" />
              <q-badge
                color="negative"
                class="tw-absolute tw-top-2 tw-right-2 tw-text-[14px] tw-px-3 tw-py-[2px] tw-rounded-none w-min-w-[70px]"
                v-if="item.coatStock"
                >{{
                  Math.round(100 - (item.coat / item.coatStock) * 100)
                }}
                %</q-badge
              >
            </div>

            <q-card-section class="tw-p-2">
              <div class="tw-text-[16px]">{{ item.name }}</div>
              <div class="text-subtitle2 tw-text-[20px] tw-flex">
                <p class="tw-font-bold tw-mr-3">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coat)
                  }}₫
                </p>
                <p class="tw-text-[18px] tw-line-through" v-if="item.coatStock">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coatStock)
                  }}₫
                </p>
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
      </div>
      <!-- end giay cong so nam -->
      <!-- giay da nam -->
      <div v-if="type === 3">
        <p class="tw-text-[24px] tw-text-center tw-mt-8 tw-mb-4">Giày Da Nam</p>
        <div
          class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
        >
          <q-card
            class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
            v-for="item in data"
            :key="item.id"
            @click="router.push(`/${item.id}`)"
          >
            <div class="tw-flex tw-relative">
              <img :src="item.src" />
              <q-badge
                color="negative"
                class="tw-absolute tw-top-2 tw-right-2 tw-text-[14px] tw-px-3 tw-py-[2px] tw-rounded-none w-min-w-[70px]"
                v-if="item.coatStock"
                >{{
                  Math.round(100 - (item.coat / item.coatStock) * 100)
                }}
                %</q-badge
              >
            </div>

            <q-card-section class="tw-p-2">
              <div class="tw-text-[16px]">{{ item.name }}</div>
              <div class="text-subtitle2 tw-text-[20px] tw-flex">
                <p class="tw-font-bold tw-mr-3">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coat)
                  }}₫
                </p>
                <p class="tw-text-[18px] tw-line-through" v-if="item.coatStock">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coatStock)
                  }}₫
                </p>
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
      </div>
      <!-- end giay da nam -->
      <!-- giay luoi nam -->
      <div v-if="type === 4">
        <p class="tw-text-[24px] tw-text-center tw-mt-8 tw-mb-4">
          Giày Lười Nam
        </p>
        <div
          class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
        >
          <q-card
            class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
            v-for="item in data"
            :key="item.id"
            @click="router.push(`/${item.id}`)"
          >
            <div class="tw-flex tw-relative">
              <img :src="item.src" />
              <q-badge
                color="negative"
                class="tw-absolute tw-top-2 tw-right-2 tw-text-[14px] tw-px-3 tw-py-[2px] tw-rounded-none w-min-w-[70px]"
                v-if="item.coatStock"
                >{{
                  Math.round(100 - (item.coat / item.coatStock) * 100)
                }}
                %</q-badge
              >
            </div>

            <q-card-section class="tw-p-2">
              <div class="tw-text-[16px]">{{ item.name }}</div>
              <div class="text-subtitle2 tw-text-[20px] tw-flex">
                <p class="tw-font-bold tw-mr-3">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coat)
                  }}₫
                </p>
                <p class="tw-text-[18px] tw-line-through" v-if="item.coatStock">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coatStock)
                  }}₫
                </p>
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
      </div>
      <!-- end giay luoi nam -->
      <!-- giay the thao nam -->
      <div v-if="type === 5">
        <p class="tw-text-[24px] tw-text-center tw-mt-8 tw-mb-4">
          Giày Thể Thao Nam
        </p>
        <div
          class="tw-grid xl:tw-grid-cols-4 sm:tw-grid-cols-3 xs:tw-grid-cols-2 tw-gap-4"
        >
          <q-card
            class="my-card tw-w-full tw-cursor-pointer hover:tw-bg-gray-100"
            v-for="item in data"
            :key="item.id"
            @click="router.push(`/${item.id}`)"
          >
            <div class="tw-flex tw-relative">
              <img :src="item.src" />
              <q-badge
                color="negative"
                class="tw-absolute tw-top-2 tw-right-2 tw-text-[14px] tw-px-3 tw-py-[2px] tw-rounded-none w-min-w-[70px]"
                v-if="item.coatStock"
                >{{
                  Math.round(100 - (item.coat / item.coatStock) * 100)
                }}
                %</q-badge
              >
            </div>

            <q-card-section class="tw-p-2">
              <div class="tw-text-[16px]">{{ item.name }}</div>
              <div class="text-subtitle2 tw-text-[20px] tw-flex">
                <p class="tw-font-bold tw-mr-3">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coat)
                  }}₫
                </p>
                <p class="tw-text-[18px] tw-line-through" v-if="item.coatStock">
                  {{
                    Intl.NumberFormat("en-VI", {
                      currency: "VND",
                    }).format(item.coatStock)
                  }}₫
                </p>
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
      </div>
      <!-- end giay the thao nam -->
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const type = ref(1);
const standard = ref({
  min: 210000,
  max: 400000,
});
const datas = ref([
  {
    id: 1,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 220000,
    coatStock: 300000,
  },
  {
    id: 2,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 260000,
    coatStock: 300000,
  },
  {
    id: 3,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 215000,
    coatStock: 300000,
  },
  {
    id: 4,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 210000,
    coatStock: "",
  },
  {
    id: 5,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 280000,
    coatStock: 300000,
  },
  {
    id: 6,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 250000,
    coatStock: 300000,
  },
  {
    id: 7,
    src: "https://agiay.vn/wp-content/uploads/2023/03/ag0221-500x500.jpg",
    name: "Giày Lười Da Bò Nam",
    coat: 320000,
    coatStock: 400000,
  },
]);
const data = ref([]);
const research = () => {
  data.value = datas.value.filter(
    (item) => item.coat >= standard.value.min && item.coat <= standard.value.max
  );
};
onMounted(() => {
  research();
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
</style>
