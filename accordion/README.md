# CSS ONLY COMPONENTS

## Accordion

##### How it works?

1. Accordion Structure

    ```
        <ul class="accordion">
            <li class="accordion__child">
                <input class="accordion__child--input" type="checkbox" name="accordion" id="item1" checked>
                    <label for="item1" class="accordion__child--label">
                        <span class="accordion__child--title">Accordion Title 1</span>
                        <span class="accordion__child--icon"></span>
                    </label>
                    <div class="accordion__child--content">
                        Bacon ipsum dolor amet tongue tri-tip andouille sausage pastrami bresaola salami jowl pork ball tip.
                    </div>
            </li>
            <li class="accordion__child">
                <input class="accordion__child--input" type="checkbox" name="accordion" id="item2" >
                    <label for="item2" class="accordion__child--label">
                        <span class="accordion__child--title">Accordion Title 1</span>
                        <span class="accordion__child--icon"></span>
                    </label>
                    <div class="accordion__child--content">
                        Bacon ipsum dolor amet tongue tri-tip andouille sausage pastrami bresaola salami jowl pork ball tip.
                    </div>
            </li>
            ----------
    ```

    1.1. You need to have a parent element width the class "accordion" and the childs with the "accordion-child" class also.

    1.2. Inside the accordion-child element, you will need an input checkbox(or radio) with and id

    1.3. Also inside the accordion-child element, you will need a label with a for attribute, that matches the id from above.

    1.4. You also need an element with the class "accordion__child--content", where you put the content from the accordion that is hidden by default.

---

2. The CSS magic
    ```
      .accordion__child--content {
          max-height: 0;
          padding:0;
          width:100%;
          overflow: hidden;
          opacity:0;
          transition: max-height .15s ease-out,  padding .3s ease-out, opacity .3s ease-out;
        }


        .accordion__child--input:checked ~ .accordion__child--content {
          max-height: 10000px;
          padding-top: 10px;
          opacity:1;
          transition: max-height 1s ease-in,  padding .3s ease-in, opacity .3s ease-in;
          overflow:visible;
        }
    ```

    2.1 This means that when your input is checked, the accordion child content will change the 'max-height' - 'padding-top' and 'opacity' values and animate them every time that you check or uncheck the accordion element.
