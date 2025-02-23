---
# You can also start simply with 'default'
theme: default
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

 <p>
        <span>Let's dive into quickly building efficient UIs with</span
        > <span class="green-text">Nuxt UI</span>!
  </p>🎨💻

<style> 
.green-text {
  color: #00DC82;
} 
</style>

<!--
# SLIDE 1
-->

---

## Table of Content

<br />

### Buttons

<div v-click>

🟢 Primary buttons. Setting up global styles (branch: primary-buttons)

</div>

<div v-click>

🟢 Example of secondary and accent buttons

</div>

<div v-click>

🟢 Change the shape (structual styles) of buttons.

</div>
<div v-click>

🟢 Change the variant of buttons

</div>
<div v-click>

🟢 Change the hover styles of buttons. (Including, hover bg color and How to make a button outline on hover, when outline is primary or antoher color.)

</div>

<div v-click>

🟢 How to add icons to buttons. Leading and trailing with icons from iconify and with icons from our svg components.

</div>

<div v-click>

🟢 how to create Buttons with icons that are animated

</div>
<div v-click>

🟢 Change icon's color inside a button

</div>

<div v-click>

🟢 white, gray and black buttons

</div>

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

</style>

<!--
# SLIDE 3
-->

---

And that’s it! 🎉 By default, Nuxt UI ships buttons as `primary`. You can check Nuxt UI’s [button config object](https://ui.nuxt.com/components/button#config) for reference.

In the `suite-starter`, the `color` property is not overridden in the `app.config.ts` file. Therefore, by default, all buttons are `primary`, and **no additional configuration is needed**.

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

Now, you can use the `UButton` component like this:

```html
<UButton :label="t('buttons.workshop.primary')" />
```

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

<div class="flex items-center space-x-4">
<img src="/images/btn-secondary.png" width="80">
<img src="/images/btn-accent.png" width="80">
</div>

<p>Set the <code>secondary</code> or <code>accent</code> color globally by following these steps:</p>

<div v-click>

<p>1️⃣ If you have a custon color, define it in <code>tailwind.config.js</code></p>

<div v-click class="flex flex justify-around">

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

</div>

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

pre {

  font-size: 14px;
} 

</style>

<!--
# SLIDE 5
-->

---

<p>2️⃣ Set the corresponding <code>color</code>as the default button color in <code>app.config.ts</code></p>

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

<p>💡 If most buttons are primary but you need a <code>secondary</code> or <code>accent</code> button on a per-button basis, use the <code>color</code> prop in the <code>UButton</code> component. You still need to define your custom color in <code>tailwind.config.js</code>.</p>

```vue
<UButton color="green" :label="t('buttons.workshop.secondary')" />
```

<img src="/images/btn-secondary.png" width="80">

<br />

```vue
<UButton color="yellow" :label="t('buttons.workshop.accent')" />
```

<img src="/images/btn-accent.png" width="80">

<!--
# SLIDE 7
-->

---

### Accent Buttons

For accent buttons we have the same 2 possibilities that we have for secondary buttons

A. If all the buttons in the page are `accent`, set up the accent color in the `app.config.ts` file.

1. First define the accent color in `tailwind.config.js`

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

        yellow: {
          ...colors.yellow, // Spread the existing green color object
          500: '#facc15', // Override the 500 shade with your secondary color
        },
      },
```

<!--
# SLIDE 8
-->

---

2. Then use yellow as the default color of buttons in `app.config.ts`

```js
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
        color: 'green',
        size: 'xl',
      },
    },
```

<!--
# SLIDE 8
-->

---

B. If most of the buttons are primary and just a couple of them are accent, use the the `color` prop in the `UButton` component.

```vue
<UButton color="yellow">
      This is an accent button
</UButton>
```

<!--
# SLIDE 9
-->

---

## Change the shape (structual styles) of buttons

What can I change?

<div class="text-sm">

- Shape
</div>

<table>
  <thead>
    <tr>
      <th>What do I need to change?</th>
      <th>Which property of the button object should I target?</th>
      <th>Result</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Border Radius</td>
      <td><code>rounded: 'rounded-md',</code> </td>
      <td><img src="/images/rounded-none-btn.png" width="80"></td>
    </tr>
     <tr>
      <td>Padding</td>
      <td> 
       The desired size inside the <code>padding</code> object. By default, the suite-starter has size <code>xl</code> for buttons.
        <pre><code>padding: {
 xl: 'px-10 py-2.5'
},</code></pre> 
      </td>
      <td><img src="/images/padding-btn.png" width="80"></td>
    </tr>
      <tr>
      <td>Font size</td>
      <td> The desired size inside the <code>size</code> object. By default, the suite-starter has size <code>xl</code> for buttons.
        <pre><code>size: {
 xl: 'text-4xl'
},</code></pre>  </td>
      <td><img src="/images/font-size-btn.png" width="80"></td>
    </tr>
     <tr>
      <td>Font weight</td>
      <td><code>font: 'font-thin',</code> </td>
      <td><img src="/images/font-weight-btn.png" width="80"></td>
    </tr>
  </tbody>
</table>

<style>


  table {
    width: 100%;
    border-collapse: collapse;
    border: 1px solid #ddd;
    font-size: 12px;
  }
  th, td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid #ddd;
    border-right: 1px solid #ddd; /* Add right border */
  }
  th {
    background-color: #d4edda;
    font-weight: bold;
    color: green;
  }
   td:last-child, th:last-child {
    border-right: none; /* Remove right border from last column */
  }
  img {
    display: block;
    margin: auto;
  }
</style>
<!--
# SLIDE 10
-->

---

## What if I want my buttons to have a different shape, such as a skewed shape?

There are 2 different ways of achieving that.

Option A. Set up skewed buttons globally in `app.congig.ts`, by targetting the `base `property inside the `button` object:

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

```ts {*|2|}

    button: {
      base: '-skew-x-12',
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
````

<!--
# SLIDE 10
-->

---

Important! By choosing option A, I would be applying the skewed style to all my buttons, regardless of their variaty or color. And this implies overridig the skew class for buttons that are not supposed to be skewed, like the button in the header.

insert image of sweked btn

<div>

```html
<UButton
  color="gray"
  variant="ghost"
  icon="heroicons:globe-alt"
  size="sm"
  :label="locale"
  :ui="{ base: '-skew-x-0' }"
/>
```

<img
  v-click
  class="absolute bottom-24 left-16 w-24 opacity-50"
  src="/images/arrow-left.png"
  alt=""
/>

</div>

insert image of non sweked btn

<!--
# SLIDE 11
-->

---

Option B. Set up skewed buttons globally in `app.congig.ts`, by targetting only the `variant` of your skewed buttons inside the `button` object:

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

<v-click>

This way buttons having a variant other than `solid`, like the buttons in the header, won't be skewed!

</v-click>

<!--
# SLIDE 12
-->

---

## Change the variant of your buttons

- By default Nuxt UI ships buttons with variant `solid`, which is not being overrriden in the suite-starter
- If you want all the buttons in the page to be a variant different from `solid`, set it globally by targetting the property `variant` inside the `default`object.

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
        variant: 'outline',
      },
    },
```

- If you want just a couple of buttons to be a specific variant use in the `variant` prop inside the `<UButton>` component.

```html
<UButton variant="solid">Button</UButton>
```

<!--
# SLIDE 13
-->

---

## Change the styles of buttons on hover. Explain variant vs color here?

### Change on hover buttons' bg color globally

1. Identify the variant of all your buttons. For example `solid`
2. Target the `solid` property inside the `variant`.
3. Add as backgrond color a different shade of your buttons' color:

```ts
    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
        solid: 'bg-{color}-500 hover:bg-{color}-200',
      },
      default: {
        size: 'xl',
      },
    },
```

or....

<!--
# SLIDE 14
-->

---

add as backgrond color a totally different color. Don't forget to definde the color in `tailwind.config.js`:

```js

     lemon: {
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
```

```ts

    button: {
      color: {
        gray: {
          shadow: 'shadow-none',
        },
      },
      variant: {
        outline: 'ring-1',
        solid: 'bg-{color}-500 hover:bg-lemon-500',
      },
      default: {
        size: 'xl',
      },
    },
```

<!--
# SLIDE 15
-->

---

## Change hover backgound color of a particular button by using the `ui`prop.

```html
<UButton :ui="{ variant: { solid: 'bg-{color}-500 hover:bg-lemon-500' } }">
  Button
</UButton>
```

<!--
# SLIDE 16
-->

---

## How to make a buttons outline on hover

1. Go to the `button`object and add the `solid` property to the `variant`object:

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

---

2. Add or change the necessary classes to have the outline style on hover

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
        solid: 'ring-2 ring-{color}-500 hover:bg-transparent hover:text-primary-500 transition-all',
      },
      default: {
        size: 'xl',
      },
    },
```
````

<!--

# SLIDE 17

-->

---

Important: if you want to have an outline colour different from your buttons' color, just don't forget to define the custom color in `tailwind.config.js`. Then, use the color as in step 2.

```ts
solid: 'ring-2 ring-{color}-500 hover:ring-lemon-500 hover:bg-transparent hover:text-lemon-500 transition-all',
```

As always, use the `ui` prop if you just want a specific button to have be outline on hover.

```html
<UButton
  :ui="{ variant: { solid: 'ring-2 ring-{color}-500 hover:ring-orange-500 hover:bg-transparent hover:text-orange-500 transition-all' } }"
>
  Button
</UButton>
```

<!--

# SLIDE 18

-->

---

## How to add icons to buttons. Leading and trailing with icons from iconify and with icons from our svg components.

Here we have different possibilities:

<v-click>

1. Add Leading or trailing icons, where the icons come from iconify

</v-click>

<v-click>

2. Add Leading or trailing icons, where the icons come from our svg component

</v-click>

<v-click>Let's explore them </v-click>

<!--

# SLIDE 19

-->

---

## Add Leading or trailing icons, where the icons come from iconify

By default Nuxt UI ships buttons with leading icons, i.e. the icon is preceeds the label. Therefore, If you add an icon to a button like this, you'll get the following button:

```html
<UButton icon="i-heroicons-pencil-square" label="Button" />
```

<img src="/images/leading-btn-iconify.png" width="80">

<p class="text-xs"> Nevertheless, you can use the <code>leading</code> and <code>trailing</code> props to set the icon position.</p>

<table>
  <thead>
    <tr>
      <th>Prop</th>
      <th>Result</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>trailing: true</code></td>
      <td>add image</td>
    </tr>
    <tr>
      <td><code>trailing: false</code></td>
      <td>add image</td>
    </tr>
    <tr>
      <td><code>leading: false</code></td>
      <td>add image</td>
    </tr>
  </tbody>
</table>

<style>
  table {
    width: 100%;
    border-collapse: collapse;
    border: 1px solid #ddd;
    font-size: 12px;
  }
  th, td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid #ddd;
    border-right: 1px solid #ddd; /* Add right border */
  }
  th {
    background-color: #34d399;
    font-weight: bold;
    color: white;
  }
   td:last-child, th:last-child {
    border-right: none; /* Remove right border from last column */
  }
  img {
    display: block;
    margin: auto;
  }
</style>

<!--

# SLIDE 20

-->

---

## Add Leading or trailing icons, where the icons come from our svg component

1. Use the `#leading`or `#trailing` slot to set the content of the icon.

```html
<UButton label="Button">
  <template #trailing> </template>
</UButton>
```

2. Use your icon component as you normally do inside the slot

```html
<UButton label="Button">
  <template #trailing>
    <Heart class="mx-auto h-[38px]" />
  </template>
</UButton>
```

<img src="/images/btn-icon-trainling-custom.png" alt="" class="w-24" />

<!--

# SLIDE 21

-->

---

## How to create Buttons with icons that are animated

Example 1 ADD IMAGES OR BETTER TRY TO HAVE A SCREEN RECORDING

If you want to create the animation globally, follow these steps. If you want to apply the animation to a specific button, just do the same using the `ui` prop.

1. Inside the `button`object, identify the class that is wrapping the label and the icon. Note: By default that class is `inline`. But if you are using the `block` prop to make the Button fill the width of its container ([See example in documentation](https://ui.nuxt.com/components/button#block)), then the wrapper class will be `block`.

```ts
  button: {
      inline: '',
      // ...rest of the object
  },
```

2. Add a transition

```ts
  button: {
      inline: 'transition-all',
      // ...rest of the object
  },
```

<style> 
p, li {
  font-size: 12px;
} 
</style>

<!--

# SLIDE 22

-->

---

3. Target the corresponding class inside the `gap` object and add the necessary gap to the default and hover states to fit your design

```ts
  button: {
      inline: 'transition-all',
      gap: {
        xl: 'gap-x-2.5 hover:gap-x-5',
      },
      // ...rest of the object
  },
```

4. Use the button component

```html
<UButton
  label="Button"
  icon="streamline-emojis:backhand-index-pointing-right-1"
  :trailing="true"
/>
```

<!--

# SLIDE 22

-->

---

Example 2 ADD IMAGES OR BETTER TRY TO HAVE A SCREEN RECORDING

1. Like in the previous example, inside the `button`object, identify the class that is wrapping the label and the icon.

```ts
  button: {
      inline: '',
      // ...rest of the object
  },
```

2. Add the group class. ([See tailwind documentation about the group class](https://v3.tailwindcss.com/docs/hover-focus-and-other-states#styling-based-on-parent-state))

```ts
  button: {
      inline: 'group',
      // ...rest of the object
  },
```

3. Add the necessary classes to the `base` property inside the `icon` object order to make you icon rotate 180° on hover

```ts
  button: {
      inline: 'group',
      icon: {
        base: 'transition-transform duration-300 group-hover:rotate-180',
      },
      // ...rest of the object
  },
```

<!--

# SLIDE 23

-->

<style> 
p, li {
  font-size: 12px;
} 
</style>

---

4. Use the button component

```html
<UButton
  label="Button"
  icon="streamline-emojis:backhand-index-pointing-up-1"
  :trailing="true"
/>
```

<!--

# SLIDE 24

-->

---

## Change icon's color inside a button

ADD IMAGES

By default the icon inside a button take the same color than the button's text.

To globally change the icon's color, add the desired text color class to the `base` property inside the `icon` object. Always remember to define your custom color in `tailwind.config.js`.

```ts
  button: {
      icon: {
        base: 'text-lemon-400',
      },
      // ...rest of the object
  },
```

If you want to change the icon color in a particular button, use the `ui` prop.

```html
<UButton
  label="Button"
  icon="material-symbols:account-circle"
  :ui="{ icon: { base: 'text-lemon-400' } }"
/>
```

<!--

# SLIDE 25

-->

---

## white, gray and black buttons

You can also use the `white`, `gray` and `black` colors in your buttons, whether globally or by using the `color` prop.

ADD IMAGES

```ts
  button: {
     // ...rest of the object
      default: {
        color: 'white',
        size: 'xl',
      },
  },
```

```html
<UButton label="Button" icon="material-symbols:account-circle" color="white" />
```

If you have buttons with such colors, take into account that Nuxt UI provides pre-defined variants with those colors inside the `button` object. Therefore, if you need to costumize styles for buttons with such colors, do it in the corresponding variant property inside the 'color' object. Let's see an example in the next slide.

<!--

# SLIDE 26

-->

---

For example, you have a white button variant ghost:

```ts

  button: {
    // ...rest of the object
       default: {
        size: 'xl',
        color: 'white',
        variant: 'ghost',
      },
  },
```

ADD IMAGES

You want to change the font color to be `text-lemon-500`. Change the class in the `ghost` property inside the `white` object:

```ts

  button: {
    // ...rest of the object
    color: {
      white: {
        ghost: 'text-lemon-500'
    },
  },
  default: {
    size: 'xl',
    color: 'white',
    variant: 'ghost',
  },
  },
```

ADD IMAGES

<!--

# SLIDE 27

-->

<style> 
p {
  font-size: 12px;
} 
</style>

---

## Thank you for your attention

<!--

# SLIDE 28

-->

---
