<template>
    <component 
    :is="type === 'numbers' ? 'ol' : 'ul'" 
    :class="classes">
        <slot/>
    </component>
</template>

<script>

export default {

  props: {
    type: {
      type: String,
      default: 'bullets',
      validator: function (value) {
        return ['plus', 'numbers', 'bullets'].indexOf(value) !== -1;
      }
    },
  },

   computed: {
        classes() {
            return {
                [`list__${this.type}`]: this.type,
            };
        },
    },


}
</script>

<style scoped>

    ul, ol {
        font-weight: bold;
        list-style: none; 
    }

    ul *:not(li):not(:first-child) {
        font-weight: 400;
    }

    ol *:not(li):not(:first-child) {
        font-weight: 400;
    }

    li:not(:last-child) {
        margin-bottom: var(--gap);
    }

    li strong {
        font-weight: 600 !important;
    }

    ul li a,
    ol li a {
      font-weight: 600 !important;
    }


    /* PLUS */
    .list__plus li {
        background: url('/plus.svg') no-repeat 0 5px;
        padding-left: var(--gap);
    }

    .list__plus li::before {
        display: none;
    }


    .list__bullets li::before {
        content: "\2022" !important;
        color: var(--color-second) !important;
        font-weight: bold; 
        display: inline-block;
        width: 1em; 
        line-height: 1.8;
        flex-shrink: 0;
    }

    .list__bullets li > ul li {
        font-weight: 400;
        padding-left: var(--gap);
    }

    .list__bullets li > ul li:first-child {
        margin-top: calc(var(--gap) * 0.5);
    } 

    .list__bullets li > ul li::before {
        content: "\25E6" !important;
        color: var(--color-actions) !important;
    }
    

    .list__plus:not(li):not(:first-child) {
        font-weight: 600;
    }
    /* PLUS end of */

    /* NUMBERS */

    .list__numbers li {
        counter-increment: number;
        padding-left: var(--gap);
        position: relative;
    }

    .list__numbers li:before {
        content: counter(number);
        font-family: var(--font-secondary);
        font-size: calc(var(--font-size) * 1.5);
        font-weight: bold;
        left: 0;
        line-height: 1.2;
        position: absolute;
        top: 0;
    }

    .list__numbers li{
        counter-increment: unset;
    }

    .list__numbers > li{
        counter-increment: number;
    }

    .list__numbers li > .list__numbers li {
        counter-increment: subNumber
    }

    .list__numbers li > .list__numbers li::before {
        content: counter(subNumber);
    }
    /* NUMBERS end of */

    @media screen and (max-width: 570px) {
        .list__numbers li {
            padding-left: 10px;
        }

        .list__numbers li::before {
            margin-left: -1rem;
        }

        
    }
</style>