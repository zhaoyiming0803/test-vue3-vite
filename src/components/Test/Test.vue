<template>
  <div>{{ msg }}</div>
</template>

<script>
import {
  GuardEventsCamelToKebabMap,
  AuthingGuard as NativeAuthingGuard
} from "@authing/native-js-ui-components";

console.log('GuardEventsCamelToKebabMap: ', GuardEventsCamelToKebabMap)
console.log('NativeAuthingGuard: ', NativeAuthingGuard)

export default {
  data () {
    return {
      msg: 123
    }
  }
}
</script>