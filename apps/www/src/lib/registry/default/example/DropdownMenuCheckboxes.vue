<script lang="ts" setup>
import type { DropdownMenuCheckboxItemProps } from 'radix-vue'
import { Button } from '@/lib/registry/default/ui/button'
import {
  DropdownMenu,
  DropdownMenuCheckboxItem,
  DropdownMenuContent,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from '@/lib/registry/default/ui/dropdown-menu'
import { ref } from 'vue'

type Checked = DropdownMenuCheckboxItemProps['checked']

const showStatusBar = ref<Checked>(true)
const showActivityBar = ref<Checked>(false)
const showPanel = ref<Checked>(false)
</script>

<template>
  <DropdownMenu>
    <DropdownMenuTrigger as-child>
      <Button variant="outline">
        Open
      </Button>
    </DropdownMenuTrigger>
    <DropdownMenuContent class="w-56">
      <DropdownMenuLabel>Appearance</DropdownMenuLabel>
      <DropdownMenuSeparator />
      <DropdownMenuCheckboxItem
        v-model:checked="showStatusBar"
      >
        Status Bar
      </DropdownMenuCheckboxItem>
      <DropdownMenuCheckboxItem
        v-model:checked="showActivityBar"
        disabled
      >
        Activity Bar
      </DropdownMenuCheckboxItem>
      <DropdownMenuCheckboxItem
        v-model:checked="showPanel"
      >
        Panel
      </DropdownMenuCheckboxItem>
    </DropdownMenuContent>
  </DropdownMenu>
</template>
