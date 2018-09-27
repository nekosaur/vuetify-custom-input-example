<script>
import VInput from 'vuetify/es5/components/VInput'
import VBtn from 'vuetify/es5/components/VBtn'
import VIcon from 'vuetify/es5/components/VIcon'
import VChip from 'vuetify/es5/components/VChip'

export default {
  extends: VInput,

  methods: {
    genDefaultSlot () {
      return [
        this.genLabel(),
        this.genCustomInput(),
        ...this.genButtons()
      ]
    },
    genCustomInput () {
      return this.$createElement(VChip, {
        props: {
          color: this.validationState
        }
      }, [this.internalValue])
    },
    genButtons () {
      const v = this.internalValue.split()
      return [
        this.$createElement(VBtn, {
          props: {
            small: true,
            icon: true
          },
          on: {
            click: () => {
              this.$emit('input', (Number(this.internalValue) + 1).toString())
            }
          }
        }, [this.$createElement(VIcon, ['add'])]),
        this.$createElement(VBtn, {
          props: {
            small: true,
            icon: true
          },
          on: {
            click: () => {
              this.$emit('input', (Number(this.internalValue) - 1).toString())
            }
          }
        }, [this.$createElement(VIcon, ['remove'])])
      ]
    }
  }
}

</script>

<style>

</style>
