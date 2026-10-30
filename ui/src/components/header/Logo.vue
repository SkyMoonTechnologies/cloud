// Licensed to the Apache Software Foundation (ASF) under one
// or more contributor license agreements.  See the NOTICE file
// distributed with this work for additional information
// regarding copyright ownership.  The ASF licenses this file
// to you under the Apache License, Version 2.0 (the
// "License"); you may not use this file except in compliance
// with the License.  You may obtain a copy of the License at
//
//   http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing,
// software distributed under the License is distributed on an
// "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
// KIND, either express or implied.  See the License for the
// specific language governing permissions and limitations
// under the License.

<template>
  <div v-if="$config.logo" class="skymoon-brand" :class="{ 'skymoon-brand-collapsed': collapsed }">
    <img
      class="skymoon-brand-mark"
      :src="collapsed ? ($config.minilogo || $config.logo) : $config.logo"
      alt="SkyMoon Cloud" />
    <span v-if="!collapsed" class="skymoon-brand-name">SkyMoon <strong>Cloud</strong></span>
  </div>
</template>

<script>

export default {
  name: 'Logo',
  components: {
  },
  props: {
    title: {
      type: String,
      default: 'SkyMoon Cloud',
      required: false
    },
    showTitle: {
      type: Boolean,
      default: true,
      required: false
    },
    collapsed: {
      type: Boolean,
      default: false,
      required: false
    }
  }
}
</script>

<style lang="less" scoped>
.skymoon-brand {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  width: 100%;
  min-height: 64px;
  padding: 4px 7px;
  box-sizing: border-box;
  overflow: hidden;
}

.skymoon-brand-mark {
  flex: 0 0 36px;
  width: 36px;
  height: 36px;
  object-fit: contain;
}

.skymoon-brand-name {
  color: #0B4B6F;
  white-space: nowrap;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: -0.02em;
}

.skymoon-brand-name strong {
  font-weight: 750;
}

.skymoon-brand-collapsed {
  padding: 4px;
}
</style>
