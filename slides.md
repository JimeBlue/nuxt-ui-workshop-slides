---
# You can also start simply with 'default'
theme: default
colorSchema: dark
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Jime's Nuxt UI Workshop
info: |
  ## Find useful examples for a faster development

# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
contextMenu: false
selectable: true
---

<h1 >
   <span>Welcome to the</span> <span class="green-text">Nuxt UI</span> <span>Workshop!</span>
 </h1>

  <div class="text-left text-sm">
    <span>There is a <a href="https://bitbucket.org/airlst/nuxt-ui-workshop-examples/src/main/" target="_blank" class="link">reference repository</a> that contains all the examples and code snippets covered in each topic.</span>
    <span> You'll find a <span class="reference-branch">📂 Reference Branch</span> label indicating which branch contains the relevant code for that topic.</span>
  </div>

<style> 
.green-text {
  color: #00DC82;
} 

.text {
  color: #e2e8f0;
} 
.link {
 color:  #34d399 !important; font-size: 14px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}
.reference-branch {
  font-size: 12px;
} 

</style>

<!--
# SLIDE 1
-->

---

## Topics

<br />

### Buttons

<ul class="space-y-2 list-disc">
  <li  @click="$slidev.nav.go(3)" class="cursor-pointer w-fit w-fit">
  🟢 Primary Buttons
  </li>
  
  <li  @click="$slidev.nav.go(5)" class="cursor-pointer w-fit">
  🟢 Secondary and Accent Buttons
  </li>
  
  <li  @click="$slidev.nav.go(8)" class="cursor-pointer w-fit">
  🟢 Customize Shape and Font Styles
  </li>
  
  <li  @click="$slidev.nav.go(13)" class="cursor-pointer w-fit">
  🟢 Change the variant of buttons
  </li>
  
  <li  @click="$slidev.nav.go(14)" class="cursor-pointer w-fit">
  🟢 Customize button hover styles
  </li>
  
  <li
    @click="$slidev.nav.go(18)" class="cursor-pointer w-fit">
  🟢 How to add icons to buttons
  </li>
  
  <li  @click="$slidev.nav.go(20)" class="cursor-pointer w-fit">
  🟢 Change the icon color inside a button
  </li>
  
  <li  @click="$slidev.nav.go(21)" class="cursor-pointer w-fit">
  🟢 Examples of button with icon that animate on hover
  
  </li>
  
  <li  @click="$slidev.nav.go(23)" class="cursor-pointer w-fit">
  🟢 White, gray and black buttons
  </li>
</ul>

<style> 


h2, h3 {
  color: #00DC82;
  font-size: 28px;
} 

h2 {
  font-size: 28px;
} 

h3 {
  font-size: 20px;
} 

p {
  color: #e2e8f0;
  font-size: 14px;
} 

ul {
  list-style-type: none !important;
}

</style>

<!--
# SLIDE 2
-->

---

<div class="flex items-center space-x-2">
<h2>Primary Buttons</h2><img src="/images/btn-primary.png" width="80">
</div>

<p class="text-xs">📂 Reference Branch: <code>primary-buttons</code></p>

<p class="text-sm">To set up the <code>primary</code>color globally, ensure that it is properly defined in your<code>tailwind.config.js</code>file before using it in your buttons.</p>

```js
 colors: {
        brand: {
          50: '#f6f2ff',
          100: '#ede8ff',
          200: '#ded4ff',
          300: '#c7b1ff',
          400: '#ab85ff',
          500: '#9c63ff',
          600: '#8530f7',
          700: '#771ee3',
          800: '#6318bf',
          900: '#52169c',
          950: '#330b6a',
        },
  },

```

<div class="mt-6 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style> 
h2, h3 {
  color: #00DC82;
  font-size: 28px;
} 

h2 {
  font-size: 28px;
} 

h3 {
  font-size: 20px;
} 

p {
  color: #e2e8f0;
} 
.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}

</style>

<!--
# SLIDE 3
-->

---

And that’s it! 🎉 By default, Nuxt UI ships buttons as `primary`. You can check Nuxt UI’s [button config object](https://ui.nuxt.com/components/button#config) for reference.

In the `suite-starter`, the `color` property is not overridden in the `button` object. Therefore, by default, all buttons are `primary`, and **no additional configuration is needed**.

```ts
// app.config.ts
    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
      },
      default: {
        size: 'xl',
      },
    },
```

<v-click>
  <p>Now, you can use the `UButton` component like this:</p>
  
  ```html
  <UButton :label="t('buttons.workshop.primary')" />
  ```
</v-click>

<style> 
h2, h3 {
  color: #00DC82;
  font-size: 28px;
} 

h2 {
  font-size: 28px;
} 

h3 {
  font-size: 20px;
} 

p {
  color: #e2e8f0;
  font-size: 14px;
} 

a {
  color: #34d399 !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}

a:hover {
  color: #efd203 !important; 
}

 


</style>

<!--
# SLIDE 4
-->

---

<h2>Secondary and Accent Buttons</h2>
<p class="reference-branch">📂 Reference Branch: <code>btn-secondary-accent</code></p>

<p>Set the <code>secondary</code> or <code>accent</code> color globally by following these steps:</p>

<v-click>
  <p>1️⃣ If you have a custon color, define it in <code>tailwind.config.js</code></p>
  
  <div class="flex flex justify-around">
  
  ```ts
    // secondary
       colors: {
        ...
          green: {
            ...colors.green,
            500: '#04784e',
          },
        },
  ```
  
  ```ts
   // accent
       colors: {
        ....
          yellow: {
            50: '#fdfee8',
            100: '#fdffc2',
            200: '#feff87',
            300: '#fff943',
            400: '#ffea03',
            500: '#efd203',
            600: '#cea400',
            700: '#a47604',
            800: '#885c0b',
            900: '#734b10',
            950: '#432705',
          },
        },
  ```
  
  </div>
</v-click>

<div class="relative">
  <div class="flex justify-end absolute bottom-0 right-4"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>
</div>

<style> 
h2, h3 {
  color: #00DC82;

} 

h2 {
  font-size: 28px;
} 

h3 {
  font-size: 20px;
} 

p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {

  font-size: 12px;
} 

pre, code {
  font-size: 10px !important;
}


.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}





</style>

<!--
# SLIDE 5
-->

---

<p>2️⃣  Set the <code>color</code> property to the desired secondary or accent color inside the <code>default</code> object.</p>

<div  class="flex justify-around">

```ts
  // secondary
     button: {
     ....
      default: {
        color: 'green',
        size: 'xl',
      },
    },
```

```ts
 // accent
   button: {
     ....
      default: {
        color: 'yellow',
        size: 'xl',
      },
    },
```

</div>

<style> 


p {
  color: #e2e8f0;
  font-size: 14px;
} 


</style>

<!--
# SLIDE 6
-->

---

<p>💡 If most buttons are primary but you need the <code>secondary</code> or <code>accent</code> color on individual buttons, use the <code>color</code> prop in the <code>UButton</code> component. 🧠 Remember you still need to define your custom color in <code>tailwind.config.js</code>.</p>

```vue
<UButton color="green" :label="t('buttons.workshop.secondary')" />
```

<img src="/images/btn-secondary.png" width="80">

<br />

```vue
<UButton color="yellow" :label="t('buttons.workshop.accent')" />
```

<img src="/images/btn-accent.png" width="80">

<v-click>
<p>💡 If you want to customize styles further and your secondary/accent button shares the same variant as your primary button, create a new object within the <code>color</code> object to avoid affecting your primary styles.</p>

```ts
   color: {
       ....
        green: {
          solid:
            'bg-green-500 text-yellow-500 hover:bg-yellow-800',
        },
      },

```

</v-click>

<style> 


p {
  color: #e2e8f0;
  font-size: 14px;
} 


</style>

<!--
# SLIDE 7
-->

---

## Customize Shape and Font Styles

<p class="reference-branch">📂 Reference Branch: <code>btn-shape-and-font-styles</code></p>

<div v-click>

<ul>
<li class="grid grid-cols-3 border-t border-l border-r">

<p class="text-sm table-heading">What do I want to customize?</p>

<p class="text-sm table-heading">Button object property controlling this?</p>

 <p class="text-sm table-heading flex justify-center">Result</p>

 </li>

<li class="grid grid-cols-3 border-t border-l border-r">

<p class="text-sm"><code>border-radius</code></p>

<div>

```ts
rounded: 'rounded-md',
```

</div>

 <p class="flex justify-center"><img src="/images/btn-border-radius.png" width="80"></p>

 </li>

 <li class="grid grid-cols-3 border">

<p class="text-sm"><code>padding</code></p>

<div>

<p class="text-sm">The desired size inside the <code>padding</code> object. By default, the <code>suite-starter</code> has size <code>xl</code> for buttons.</p>

```ts
padding: {
 xl: 'px-10 py-2.5'
},
```

</div>

 <p class="flex justify-center items-center"><img src="/images/btn-padding.png" class="w-40"></p>

 </li>

</ul>

</div>

<div class="mb-4 mr-2 flex justify-end absolute bottom-0 right-0"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {
  font-size: 12px;
} 

.table-heading {
  color: #00DC82;
} 

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}

</style>
<!--
# SLIDE 8
-->

---

<ul>
<li class="grid grid-cols-3 border-t border-l border-r">

<p class="text-sm table-heading">What do I want to customize?</p>

<p class="text-sm table-heading">Button object property controlling this?</p>

 <p class="text-sm table-heading flex justify-center">Result</p>

 </li>

<li class="grid grid-cols-3 border-t border-l border-r">

<p class="text-sm"><code>font-size</code></p>

<div>

<p class="text-sm">The desired size inside the <code>size</code> object. By default, the suite-starter has size <code>xl</code> for buttons.</p>

```ts
size: {
 xl: 'text-4xl'
},
```

</div>

 <p class="flex justify-center items-center"><img src="/images/btn-font-size.png" class="w-36"></p>

 </li>
 <li class="grid grid-cols-3 border">

<p class="text-sm"><code>font-weight</code></p>

<div>

```ts
font: 'font-thin',
```

</div>

 <p class="flex justify-center items-center"><img src="/images/btn-font-weight.png" class="block w-40"></p>

 </li>

</ul>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.table-heading {
  color: #00DC82;
} 

</style>

<!--
# SLIDE 9
-->

---

<ul>
<li class="grid grid-cols-3 border-t border-l border-r ">

<p class="text-sm table-heading">What do I want to customize?</p>

<p class="text-sm table-heading">Button object property controlling this?</p>

 <p class="text-sm  flex justify-center">Result</p>

 </li>
<li class="grid grid-cols-3 border">

<p class="text-sm"><code>color</code></p>

<div>
<p class="text-sm">Change the class inside your button variant. By default buttons are variant solid</p>

```ts
   variant: {
        ....
        solid: 'text-yellow-200',
   },
```

</div>

 <p class="flex justify-center items-center"><img src="/images/btn-font-color.png" class="block w-40"></p>

 </li>

</ul>

<div v-click>
  <p>💡 All the mentioned styles can be configured either globally or on individual buttons using the <code>ui</code> prop. </p>

  <div>
```ts 
  <UButton :label="t('buttons.workshop.example')" :ui="{ padding: { xl: 'px-16 py-2.5' } }" />
```

  </div>
</div>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.table-heading {
  color: #00DC82;
} 

</style>

<!--
# SLIDE 10
-->

---

<div class="flex space-x-6">
  <h2>How to Create Skewed Buttons</h2>
  <img
  class="w-28"
  src="/images/btn-skewed.png"
  alt=""
/>
</div>

<p class="reference-branch">📂 Reference Branch: <code>btn-skewed</code></p>

<v-click>

<p>
  📌  Just add the necessary class/classes to the property within the <code>variant</code> object corresponding to your button`s variant.
  In this example, buttons use the <code>solid</code> variant.
</p>

````md magic-move {lines: true}
```ts

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
      },
      default: {
        size: 'xl',
      },
    },
```

```ts {*|9-10|}

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
        solid: '-skew-x-12',
      },
      default: {
        size: 'xl',
      },
    },
```
````

</v-click>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {
  font-size: 12px;
} 

</style>
<!--
# SLIDE 11
-->

---

<p>🧠 Remember you can apply the skewed styling just to a particular button by using the <code>ui</code> prop.</p>

```html
<UButton
  :label="t('buttons.workshop.example')"
  :ui="{ variant: { solid: '-skew-x-12' } }"
/>
```

<v-click>
  <p>📝 You can also create a skewed button by adding the necessary class to the <code>base</code> property. However, keep in mind that this will cause all your buttons to be skewed, regardless of their variant.</p>
  
  ```ts
  
      button: {
        base: '-skew-x-12',
        ....
      },
  ```
</v-click>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {
  font-size: 12px;
} 

</style>

<!--
# SLIDE 12
-->

---

<h2>Change the variant of buttons</h2>
<p class="reference-branch">📂 Reference Branch: <code>btn-change-variant</code></p>

<v-click>

  <p class="flex items-center space-x-2">  <span>📌 Do it globally by adding the <code>variant</code> property to the <code>default</code> object.</span>   <span>(ℹ️ by default buttons have variant <code>solid</code>)</span></p>

````md magic-move {lines: true}
```ts

    button: {
   ....
      default: {
        size: 'xl',
      },
    },
```

```ts {*|5-6|}

    button: {
  ...
      default: {
        size: 'xl',
        variant: 'outline',
      },
    },
```
````

</v-click>

<br />
<v-click>

<p>  📌 Alternatively, you can change the variant of individual buttons by using the <code>variant</code> prop.</p>

```html
<UButton variant="soft" :label="t('buttons.workshop.soft')" />
```

</v-click>

<div class="mt-16 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {
  font-size: 12px;
} 

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--
# SLIDE 13
-->

---

<h2>Customize button hover styles</h2>
<v-click>
  <h3 class="mt-4">📌 Change the background color</h3>
  <p class="text-xs">📂 Reference Branch: <code>btn-hover-change-bg-color</code></p>
</v-click>

<v-click>

1. <p><span>Identify the variant of the buttons. In this example the variant is <code>solid</code></span><span> (🧠 Remember, buttons remain solid unless you explicitly add the <code>variant</code> property to the <code>default</code> object.)</span></p>

```ts
    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
      },
      default: {
        size: 'xl',
      },
    },
```

</v-click>

<div class="mb-6 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style> 

h2 {
  color: #00DC82;
  font-size: 28px;
} 
h3 {
  color: #00DC82;
  font-size: 20px;
} 
p {
  color: #e2e8f0;
  font-size: 14px;
} 

.reference-branch {
  font-size: 12px;
} 

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--
# SLIDE 14
-->

---

2. <p>Add the class to your variant inside the <code>variant</code> object. You can add a different shade of your button's color or a custom color.</p>

```ts
  variant: {
        ....
        solid: 'hover:bg-primary-800',
  },
```

```ts
  variant: {
        ....
        solid: 'hover:bg-yellow-900',
  },
```

 <v-click>
   <p>💡 As always, use the <code>ui</code> prop if you want to change the backgound color of individual buttons.</p>
   
   ```html
   <UButton
    :ui="{ variant: { solid: 'hover:bg-yellow-900' } }"
    :label="t('buttons.workshop.hover_me')"
   />
   ```
 </v-click>

<style> 

p {
  color: #e2e8f0;
  font-size: 14px;
} 



</style>
<!--
# SLIDE 15
-->

---

  <h3 class="mt-4">📌 Make button outline on hover</h3>
    <p class="text-xs">📂 Reference Branch: <code>btn-hover-outline</code></p>
<div>

<v-click>
<p> 1. Go to the <code>button</code> object and add the <code>solid</code> property to the <code>variant</code> object.</p>

````md magic-move {lines: true}
```ts

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
      },
      default: {
        size: 'xl',
      },
    },
```

```ts {*|9-10|}

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
        solid: '',
      },
      default: {
        size: 'xl',
      },
    },
```
````

</v-click>

</div>

<style>

h2 { color: #00DC82; font-size: 28px; } h3 { color: #00DC82; font-size: 20px; } p { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; }

</style>

<!--
# SLIDE 16
-->

---

<p>2. Add or change the necessary classes to create the outline style.</p>

````md magic-move {lines: true}
```ts

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
           solid: '',
      },
      default: {
        size: 'xl',
      },
    },
```

```ts {*|9-10|}

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
        solid: 'ring-2 ring-primary hover:bg-transparent hover:text-primary-500 transition-all',
      },
      default: {
        size: 'xl',
      },
    },
```
````

<v-click>

<p>💡 The outline and text color can match the button's color or be set to any other color.</p>

</v-click>
<v-click>

<p>💡 You can create the style globally or apply it to individual buttons.</p>

</v-click>

<style>

 p { color: #e2e8f0; font-size: 14px; }



</style>

<!--
# SLIDE 17
-->

---

  <h2 class="mt-4">How to add icons to buttons</h2>
  <p class="reference-branch">📂 Reference Branch: <code>btn-add-icon</code></p>

<span class="special">📌 Using any icon from</span> [Iconify](https://icones.js.org/).

<v-click>

<p>1.  Use the <code>icon</code> prop with the desired icon.</p>

```html
<UButton icon="i-heroicons-pencil-square" />
```

</v-click>

<v-click>

<p>
  <span>2. Use the <code>leading</code> or <code>trailing</code> prop to set the icon position.</span> <span>By default, icons are<code>leading.</code></span>
    <a href="https://ui.nuxt.com/components/button#icon" target="_blank" class="link">Check out the Nuxt UI documentation.</a>
</p>

<img src="/images/btn-iconify-leading.png" width="80">

```html
<UButton icon="i-heroicons-pencil-square" />
```

<br />
<img src="/images/btn-iconify-trailing.png" width="80">

```html
<UButton icon="i-heroicons-pencil-square" :trailing="true" />
```

</v-click>

<div class="mt-6 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style>

a {
  color: #34d399 !important; 
  font-size: 20px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
} 

.link {
 color:  #34d399 !important; font-size: 14px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}

h2 { color: #00DC82; font-size: 28px; } 

.special { color: #00DC82; font-size: 20px; } 

p { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; margin-top: -2px;}

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--
# SLIDE 18
-->

---

<p class="special">📌 Using a custom icon</p>

<v-click>

   <p>1. Use the <code>#leading </code>or <code>#trailing</code> slot to set the content of the icon.</p>
  
  ```html
  <UButton label="Button">
    <template #trailing> </template>
  </UButton>
  ```
  
  <br />
</v-click>

<v-click>
  <p>2. Use your icon component inside the slot.</p>
  
  ```html
  <UButton label="Button">
    <template #trailing>
      <Brain class="w-8" />
    </template>
  </UButton>
  ```
  
  <img src="/images/btn-icon-custom-trailing.png" width="80">
</v-click>

<style>

a {
  color: #34d399 !important; 
  font-size: 20px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
} 

.link {
 color:  #34d399 !important; font-size: 14px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}

h2 { color: #00DC82; font-size: 28px; } 

.special { color: #00DC82; font-size: 20px; } 

p { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; margin-top: -2px;}

</style>

<!--

# SLIDE 19

-->

---

<h2>Change the Icon Color Inside a Button</h2>
<p class="reference-branch">📂 Reference Branch: <code>btn-change-icon-color</code></p>

<v-click>
  <p>By default the icon inside a button take the same color than the button’s text.</p>
</v-click>

<v-click>
  <p>To change the icon's color globally or for individual buttons, add a text color class to the <code>base</code> property within the <code>icon</code> object.</p>

```ts

    button: {
     ....
      icon: {
        base: 'text-yellow-300',
      },
    },
```

</v-click>

<v-click>
  <p>If you're using a custom icon, just add  a text color class within the icon's component.</p>
  
  ```html
  <UButton :label="t('buttons.workshop.example')">
    <template #trailing>
      <Trash class="w-4 text-green-500" />
    </template>
  </UButton>
  ```
</v-click>

<div class="mt-10 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style>

h2 { color: #00DC82; font-size: 28px; } 

p { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; margin-top: -2px;}

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--

# SLIDE 20

-->

---

<h2>Examples of button with icon that animate on hover</h2>
<p class="reference-branch">📂 Reference Branch: <code>btn-animated-icon</code></p>

<Button  m="t-4" />

<v-click>
<p class="text"><span>1. Inside the <code>button</code> object, identify the property that is wrapping the <code>label</code> and the <code>icon</code>.</span> <span>📝 By default that property is <code>inline</code>.   But if you are using the <a href="https://ui.nuxt.com/components/button#block" target="_blank" class="link">block</a> prop, then the wrapper property will be <code>block</code>.</span></p>

```ts
  button: {
      inline: '',
      ....
  },
```

</v-click>

 <v-click>
   <p class="text">2. Add a transition</p>
   
   ```ts
    button: {
        inline: 'transition-all',
        ....
    },
   ```
 </v-click>

 <div class="mt-6 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style>

h2 { color: #00DC82; font-size: 28px; } 
h3 { color: #00DC82; font-size: 22px; } 

.link {
 color:  #34d399 !important; font-size: 14px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}

.text { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; margin-top: -2px;}

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--

# SLIDE 21

-->

---

 <p class="text"> 3. Add the necessary gap to fit your design</p>

```ts
  button: {
      inline: 'transition-all',
      gap: {
        xl: 'gap-x-2.5 hover:gap-x-5',
      },
      ....
  },
```

<style>


.text { color: #e2e8f0; font-size: 14px; }

</style>

<!--

# SLIDE 22

-->

---

<h2>White, Gray and Black Buttons</h2>
<p class="reference-branch">📂 Reference Branch: <code>btn-white-gray-black</code></p>

<p class="text">📌  Nuxt UI provides pre-defined variants for white, gray, and black buttons. If you need to customize styles for these colors, modify the corresponding variant property inside the <code>color</code> object."</p>

<p class="text">💡 <span class="underline">Example:</span> change the text color of a <code>white</code> button variant <code>solid</code></p>

```ts
    button: {
      color: {
        white: {
          solid: 'text-primary-600',
        },
      },
      .....
    },
```

```html
<UButton color="white" variant="solid" />
```

<div class="mt-16 flex justify-end"> <button @click="$slidev.nav.go(2)" class="back"> Topics </button> </div>

<style>

h2 { color: #00DC82; font-size: 28px; } 


.link {
 color:  #34d399 !important; font-size: 14px !important; 
  text-decoration: underline !important;
  text-decoration-style: solid !important; 
  text-decoration-thickness: 1px !important; 
  text-underline-offset: 2px !important; 
  border-bottom: none !important; 
  transition: color 0.2s ease-in-out; 
}

.text { color: #e2e8f0; font-size: 14px; }

.reference-branch { font-size: 12px; margin-top: -2px;}

.back {
  color: #00DC82; 
  font-size: 12px; 
  cursor: pointer;
}

.back:hover {
  opacity: 0.5;
}


</style>

<!--

# SLIDE 23

-->

---

<div class="text">
  <p>🚀 "That’s it for today! Now let's build amazing buttons with Nuxt UI!"</p>
  <p>💚 Thanks for your time!</p>
</div>

<style>



.text { color: #e2e8f0; font-size: 14px; }



</style>
<!--

# SLIDE 24

-->

---
