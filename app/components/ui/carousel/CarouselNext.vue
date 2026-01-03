<script setup lang="ts">
import type { WithClassAsProps } from "./interface"
import type { ButtonVariants } from '@/components/ui/button'
import { ArrowRight } from "lucide-vue-next"
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

const { orientation, canScrollNext, scrollNext } = useCarousel()
</script>

<template>
  <Button data-slot="carousel-next" :disabled="!canScrollNext" :class="cn(
    'rounded-full',
    props.class,
  )" :variant="variant" :size="size" @click="scrollNext">
    <slot>
      <ArrowRight />
      <span class="sr-only">Next Slide</span>
    </slot>
  </Button>
</template>
