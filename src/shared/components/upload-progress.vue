<template>
  <div class="upload-progress h-full w-full relative">
    <fui-animation
      :animation-type="['fade']"
      :duration="100"
      :show="!value.completed"
      style="position: absolute; inset: 0"
    >
      <div class="progress flex flex-center">
        {{ value.progress }}%
      </div>
    </fui-animation>
    <slot />
  </div>
</template>

<style lang="scss" scoped>
.progress {
    z-index: 1;
    position: absolute;
    bottom: 0;
    right: 0;
    font-size: 10px;
    border-radius: 15rpx 0 0 0;
    transform: scale(0.8);
    transform-origin: 100% 100%;
    width: 80rpx;
    height: 40rpx;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
}
</style>

<script setup lang="ts">
import type { UploadTask } from '../utils/upload.service'

defineProps<{
  value: UploadTask
}>()
</script>
