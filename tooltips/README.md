# CSS ONLY COMPONENTS

## Tooltip

##### How it works?

1. Lets use the following example
    ```
        <span data-tooltip="Hello!" data-tooltip-pos="up" data-tooltip-length="fit">Hover Me</span>
    ```

2. Tooltip Content - The tooltip content is set in the data-tooltip attribute, in this case it will show "Hello!"
    ```
       data-tooltip="Hello!"
    ```
    As you can see we add the content in the css like this:
    ```
        .tooltip:after {
          content: attr(data-tooltip);
        }
    ```

3. Tooltip Position - The tooltip position related to the element is set with the data-tooltip-pos attribute. In this case the tooltip will be position in the right of the span element
    ```
        data-tooltip-pos="right"
    ```
    ---

    3.1 The tooltip will be positioned in the left of the element


            data-tooltip-pos="left"


    3.2 The tooltip will be positioned in the top of the element


            data-tooltip-pos="up"


    3.3 The tooltip will be positioned in the bottom of the element


            data-tooltip-pos="down"



4. Tooltip Width - You can define the tooltip width with the data-tooltip-lenght attribute. In this example we are using "fit", which means that the tooltip width is 100% of your content.
    ```
        data-tooltip-length="fit"
    ```
    ---

    4.1 If you set the 'data-tooltip-pos' attribute to 'small' the tooltip will have 80px width


            data-tooltip-pos="small"

            [data-tooltip-length="small"]:after {
              width: 80px;
            }


    4.2 If you set the 'data-tooltip-pos' attribute to 'medium' the tooltip will have 150px width


            data-tooltip-pos="medium"

            [data-tooltip-length="medium"]:after {
              width: 150px;
            }


    4.3 If you set the 'data-tooltip-pos' attribute to 'large' the tooltip will have 260px width


            data-tooltip-pos="large"

            [data-tooltip-length="large"]:after {
              width: 260px;
            }
