<script setup lang="ts">
// import { useRouter } from "vue-router";
import noAccess from "@/assets/status/403.svg?component";
import * as CommonAPI from "@/api/common";

defineOptions({
  name: "403"
});

async function getConfig() {
  await CommonAPI.getLoginUserInfo().then(res => {
    console.log(res);
  });
}
</script>

<template>
  <div class="flex justify-center items-center h-[640px]">
    <noAccess />
    <div class="ml-12">
      <p
        class="font-medium text-4xl mb-4 dark:text-white"
        v-motion
        :initial="{
          opacity: 0,
          y: 100
        }"
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 100
          }
        }"
      >
        403
      </p>
      <p
        class="mb-4 text-gray-500"
        v-motion
        :initial="{
          opacity: 0,
          y: 100
        }"
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 300
          }
        }"
      >
        抱歉，你无权访问该页面
      </p>
      <el-button
        type="primary"
        @click="getConfig"
        v-motion
        :initial="{
          opacity: 0,
          y: 100
        }"
        :enter="{
          opacity: 1,
          y: 0,
          transition: {
            delay: 500
          }
        }"
      >
        返回首页
      </el-button>
    </div>
  </div>
</template>
