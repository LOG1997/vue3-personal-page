<script setup lang="ts">
import { ref, reactive } from "vue";
import { ISkill } from "@/types/home";
defineProps<{
  skillItem: ISkill;
}>();
</script>

<template>
  <div class="card-item">
    <div class="card-icon">
      <svg-icon :name="skillItem.icon"></svg-icon>
    </div>
    <div class="card-title">
      <span class="card-title__title">{{ skillItem.title }}</span>
      <span class="card-title__version">{{ skillItem.version }}</span>
    </div>
    <div class="card-desc">{{ skillItem.desc }}</div>
  </div>
</template>

<style scoped lang="scss">
.card-item {
  width: 30%;
  min-width: 350px;
  height: 200px;
  margin-bottom: 80px;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  border-radius: 10px;
  transition: all 0.3s;
  cursor: pointer;
  @include themeChildify {
    background-color: themed("header-bg-color");
    box-shadow: 5px 5px 10px themed(shawdow-color);
  }
  &:hover {
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.2);
  }
  .card-icon {
    width: 100%;
    height: 100px;
    position: absolute;
    top: -40px;
    svg {
      width: 120px;
      height: 120px;
    }
  }
  .card-title {
    width: 100%;
    height: 50px;
    padding-left: 120px;
    text-align: left;
    margin-top: -30px;
    .card-title__title {
      font-weight: 600;
      font-size: 40px;
    }
    .card-title__version {
      font-size: 16px;
      color: #999;
    }
  }
  .card-desc {
    padding-left: 120px;
    padding-right: 20px;
    text-align: left;
    font-size: 16px;
    color: #999;
  }
}
</style>
