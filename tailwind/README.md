# Tailwind CSS. But make it nice

**💭 Unordered thoughts during the session**

- first impression often overwhelming

  - 🔠🥬 "Buchstabensalat"
  - new devs may have a hard time finding components in the dev tools
  - a11y auditing might complain

- ✨ **Why Tailwind?** many advantages/appealing concepts

  - "I didn't know any CSS" => Tailwind can be great to get started (and learn CSS on the way)
  - Adam Wathan wrote an [article on the different stages of writing CSS](https://adamwathan.me/css-utility-classes-and-separation-of-concerns/). For a long time there was this "Separation of Concerns" with tailwind you have the styles right next to your element

  - No more coming up with class names

- 🧠 Good to know

  - best utilised when used together with a framework (together with component structure)
  - there are [helper classes](https://tailwindcss.com/docs/hover-focus-and-other-states#using-with-your-own-classes) with config

  - adhere to the **MOIST** 💧 principle: moderate overlap is sometimes tolerable (in contrast to [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself))
  - write semantic html! (it's good practice & helps e.g. with guidance in inspector)
  - in [CSS the last statement counts](https://css-tricks.com/precedence-css-order-css-matters/) (if there are multiple style definitions of e.g. h1). In Tailwind: configuration in tailwind file counts (not in html)
  -  there are multiple helper libraries for different frameworks. E.g. [twMerge](https://www.npmjs.com/package/tailwind-merge) to merge multiple tailwind strings

🤓 **Examples**

- you need to enhance the border. There are 2 ways to change 'global' styles
  - you have something like a 'Base Box' Component (one pllace to change your style)
  - you use Design Tokens (with underlying Design System)
- sometimes it's annoying that ‘shortcuts’ for e.g. setting colours cannot be used (`bg-${color}-100`)
  - ⚡️ tailwind needs to know its classes instantly
  - 💡 example hack: use [tailwind config safelist](https://tailwindcss.com/docs/content-configuration#safelisting-classes) to e.g introduce `brand`
  - or use an object to map all alternatives `brand-1`, `brand-2`

🛣️ **When in doubt...**it's always possible to write CSS

- the systems work 'next to each other'

- ...or write regular CSS first & translate into Tailwind in the 2nd step (helpful if you don't feel confident yet or write [Animations](https://tailwindcss.com/docs/animation), that can be difficult in Tailwind)

- if you're at a dead end with standard tailwind:

  - [style scope block](https://developer.mozilla.org/en-US/docs/Web/CSS/@scope), CSS properties

  - [@apply](https://tailwindcss.com/docs/reusing-styles#extracting-classes-with-apply) (when in doubt, but don't overuse)

    > Whatever you do, **don’t use `@apply` just to make things look “cleaner”**. Yes, HTML templates littered with Tailwind classes are kind of ugly.  Making changes in a project that has tons of custom CSS is worse.

⭐️ **Library Recommendation: CVA**: [Class Variance Authority]( https://cva.style/docs) (*don't get scared off by the name ⚠️*)

- soon there will be a v1.0 => if you get started, do that with the beta v1.0 right away
- generates a string of tailwind classes
- put it next to your react component
- example on website has weird naming (adjusted example below)

```ts
const buttonClasses = cva(["font-semibold", "border", "rounded"], { 
// ...  
  
buttonClasses({ intent: "secondary", size: "small" });
// => "font-semibold border rounded bg-white text-gray-800 border-gray-400 hover:bg-gray-100 text-sm py-1 px-2"
```
