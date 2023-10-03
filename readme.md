# Tailwind UI with Vue.js For Lazy Devs

This is a collection of ui I used most in my project.

## Usages

### Silde over

```html
<SlideOver title="Customizer"
    toggleClass="p-2 z-[99999] text-white bg-indigo-600 hover:bg-indigo-700 rounded-md bottom-4 right-8 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 cursor-pointer">
    <template v-slot:toggleIcon>
      <PaintBrushIcon class="w-6 h-6" />
    </template>
    <template v-slot:content>
      <!-- Your content goes here -->
    </template>
    <template v-slot:footer>
      <button type="button"
        class="px-4 py-2 text-sm font-medium text-gray-700 bg-white border border-gray-300 rounded-md shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Cancel</button>
      <button type="submit"
        class="inline-flex justify-center px-4 py-2 ml-4 text-sm font-medium text-white bg-indigo-600 border border-transparent rounded-md shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Save</button>
    </template>
  </SlideOver>
```
