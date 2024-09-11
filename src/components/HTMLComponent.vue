<script lang="ts">
import {h} from 'vue'
import * as htmlparser2 from 'htmlparser2'
import * as domutils from 'domutils'
import {ElInput} from "element-plus";
import katex from 'katex'

function getAttributeByName(element: any, name: string) {
  for (let attr of element.attributes) {
    if (attr.name == name) return attr.value
  }
  return null
}

function recursiveRender(element) {
  console.log(element)
  const tag = element.type == 'root' ? 'div' : element.name
  if (element.type == 'text') {
    const innerHTML = element.data as string
    if (!innerHTML.includes("{{}}")) {
      return h('span', innerHTML)
    }
    const parts = innerHTML.split("{{}}")
    const output = [h('span', parts[0])]
    for (let i = 1; i < parts.length; i++) {
      output.push(h(ElInput, {
        style: 'display: inline-block;width:8rem;'
      }))
      output.push(h('span', innerHTML))
    }
    return output
  }
  if (tag === 'script') {
    const type = getAttributeByName(element, 'type')
    let text = (element.childNodes[0] as Text).data
    const display = type.match(/mode\s*=\s*display(;|\s|\n|$)/) != null
    text = katex.renderToString(text, {displayMode: display, output: 'mathml'})
    return h(display ? 'div' : 'span',
        {
          class: display ? 'equation' : 'inline-equation',
          innerHTML: text
        })
  }
  return h(tag, {...element.attribs}, domutils.getChildren(element).map((child) => {
    return recursiveRender(child)
  }))
}

export default {
  props: {
    html: {
      type: String,
      default: '<span>AHIH</span>'
    }
  },
  setup(props) {
    return () => {
      console.log(props.html)
      const element = htmlparser2.parseDocument(props.html)
      return recursiveRender(element)
    }
  },
}
</script>
