<template>
  <div class="el-avatar"
    :class="[
      avatarSize ? 'el-avatar--' + avatarSize : '',
      {        
        'is-round': round        
      }
    ]">
    <span class="el-avatar--wrapper">
      <template v-if="src">
        <img v-bind:src="src">
      </template>
      <template v-else>
        <slot></slot>
      </template>
    </span>
  </div>
</template>

<script>
  const AVATAR_SIZES = ['small', 'medium', 'large', 'extra-large'];

  export default {
    name: 'ElAvatar',
    props: {
      round: Boolean,
      src: String,
      size: {
        type: String,
        default() {
          return 'medium';
        }
      }
    },
    computed: {
      avatarSize() {
        return (AVATAR_SIZES.includes(this.size)) ? this.size : null;
      }
    }
  };
</script>
