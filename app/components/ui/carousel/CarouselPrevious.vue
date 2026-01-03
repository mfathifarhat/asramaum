<script setup lang="ts">
import type { WithClassAsProps } from "./interface"
import type { ButtonVariants } from '@/components/ui/button'
import { ArrowLeft } from "lucide-vue-next"
import { cn } from "@/lib/utils"
import { Button } from '@/components/ui/button'
import { useCarousel } from "./useCarousel"

const props = withDefaults(defineProps<{
  variant?: ButtonVariants["variant"]
  size?: ButtonVariants["size"]
}
  & WithClassAsProps>(), {
  variant: "default",
  size: "icon-lg",
})

const { orientation, canScrollPrev, scrollPrev } = useCarousel()
</script>

<template>
  <Button data-slot="carousel-previous" :disabled="!canScrollPrev" :class="cn(
    'rounded-full',
    props.class,
  )" :variant="variant" :size="size" @click="scrollPrev">
    <slot>
      <ArrowLeft />
      <span class="sr-only">Previous Slide</span>
    </slot>
  </Button>
</template>
