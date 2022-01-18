# Examples

Some examples of how to use the library are shown below.

[[toc]]

## Basic example

<script setup>
import BasicExample from './examples/BasicExample.vue'
import BasicExampleWidthHeight from './examples/BasicExampleWidthHeight.vue'
import LoopExample from './examples/LoopExample.vue'
import PauseOnHoverExample from './examples/PauseOnHoverExample.vue'
import PlayOnHoverExample from './examples/PlayOnHoverExample.vue'
import ReactiveExample from './examples/ReactiveExample.vue'
import EventExample from './examples/EventExample.vue'
</script>

<BasicExample />

```vue
<template>
  <Vue3Lottie :animationData="DogJSON" :height="200" :width="200" />
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import DogJSON from './lotties/dog.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      DogJSON,
    }
  },
}
</script>
```

## Basic example with a custom width and height

You can also pass in any valid css unit here. If you pass in a number, It will be inferenced as a `pixel` value. Some valid examples include `50%`, `10em`, etc.

<BasicExampleWidthHeight />

```vue
<template>
  <Vue3Lottie :animationData="VinylJSON" :height="300" :width="300" />
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import VinylJSON from './lotties/vinyl.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      VinylJSON,
    }
  },
}
</script>
```

## Loop example

<LoopExample />

::: info
If the loop has already been completed, refreshing the page will restart the animation.
:::

```vue
<template>
  <Vue3Lottie
    :animationData="AstronautJSON"
    :height="200"
    :width="200"
    :loop="3"
  />
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import AstronautJSON from './lotties/astronaut.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      AstronautJSON,
    }
  },
}
</script>
```

## Pause on Hover

If you set pauseOnHover to true, the animation will pause when you hover over the animation.

<PauseOnHoverExample />

```vue
<template>
  <Vue3Lottie
    :animationData="RocketJSON"
    :height="200"
    :width="200"
    :pauseOnHover="true"
  />
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import RocketJSON from './lotties/rocket.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      RocketJSON,
    }
  },
}
</script>
```

## Play on Hover

The lottie animation will play when you hover over the animation. Moving the mouse away will pause the animation at its current frame. Hovering over the container will play the animation from where it left off.

<PlayOnHoverExample/>

```vue
<template>
  <Vue3Lottie
    :animationData="WifiJSON"
    :height="200"
    :width="200"
    :playOnHover="true"
  />
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import WifiJSON from './lotties/wifi.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      WifiJSON,
    }
  },
}
</script>
```

## Reactive Example

You can also use the `pauseAnimation` prop to control the play and pause state of the lottie animation.

<ReactiveExample/>

```vue
<template>
  <div>
    <Vue3Lottie
      :animationData="CarJSON"
      :height="200"
      :width="200"
      :pauseAnimation="playState"
    />
    <button @click="playState = !playState">Play/Pause Animation</button>
  </div>
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import CarJSON from './lotties/car.json'

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      playState: false,
      CarJSON,
    }
  },
}
</script>
```

## Events Example

`vue3-lottie` has support for events to be emitted from the animation.

<EventExample/>

```vue
<template>
  <div>
    <Vue3Lottie
      :animationData="ClockJSON"
      :height="200"
      :width="200"
      @onLoopComplete="completed++"
    />
    <span> This animation has completed {{ completed }} times. </span>
  </div>
</template>

<script>
import Vue3Lottie from 'vue3-lottie'
import ClockJSON from './lotties/clock.json'

export default {
  name: 'EventExample',
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      ClockJSON,
      completed: 0,
    }
  },
}
</script>
```

::: info Disclaimer
All the lotties in this page are from [lottiefiles.com](https://lottiefiles.com/).
:::