# Butter list items

I built this list item as a Polymer component, that can be slided sideways. If slided to the right it slides ot out view, and if slided to the left it bounces back to the initial position. When slided out view, clicked at, or tapped at events will be fired for each corresponding action. The consumer can add item text and id to the component through the bindings "text" and "id".

It's kind of a work in progress at the moment, so I havn't had time to add to much documentation yet.

## Installation and demo

1. Install `bower` and `polymer-cli`:

        npm install -g bower polymer-cli

2. Clone the repo:

        git clone git@github.com:HenrikGudmundsson/butter-list-items.git

3. Run bower dependencies from the root folder:

        bower install

4. Run the demo application in the browser:

        polymer serve --open

5. Your browser should automatically open the demo page with a list containing the items, ready to try out!

## Inline demo

<!--
```
<custom-element-demo>
  <template>
    <link rel="import" href="sliding-list-item.html">
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
    <style>
        .title {
            font-size: 1.5rem;
            color: darkred;
            display: flex;
            justify-content: center;
            font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
            font-weight: 200;
        }
        .info {
            font-size: 2rem;
            margin-left: 2rem;
            margin-bottom:2rem;
        }

        .info {
            text-align: center;
        }
        .list {
            overflow: hidden;
        }
    </style>
    <div class="info">
        <span>(To slide on a desktop browser, you need to use your devtools and change to mobile browser simulation.)</span>
    </div>
    <div class="list">
        <sliding-list-item text="First item" id="1"></sliding-list-item>
        <sliding-list-item text="Second item" id="2"></sliding-list-item>
        <sliding-list-item text="Third item" id="3"></sliding-list-item>
        <sliding-list-item text="Fourth item" id="4"></sliding-list-item>
        <sliding-list-item text="Fifth item" id="5"></sliding-list-item>
        <sliding-list-item text="Sixth item" id="6"></sliding-list-item>
    </div>

    <script>
        class DemoComponent extends Polymer.Element {
            static get is() { return 'demo-component' }

            constructor() {
                super();

                this.message = 'Click, tap or slide the list items';

                document.addEventListener('slider-list-item-removed', (e)=> {
                    this.message = `Item removed - ID: ${ e.detail.id }`;
                });
                document.addEventListener('slider-list-item-clicked', (e)=> {
                    this.message = `Item clicked - ID: ${ e.detail.id }`;
                });
            }
        }

        customElements.define(DemoComponent.is, DemoComponent);
    </script>
```

## License

MIT