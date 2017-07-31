# CSS ONLY COMPONENTS

## Modal

##### How it works?

1. You will need a link to open the modal (you need to fill the href)
    ```
        <a href="#modalDialog">Open Modal!</a>
    ```

2. Modal Structure

    ```
        <section id="modalDialog" class="modalDialog" role="dialog" aria-labelledby="modal-label" aria-hidden="true">
            <div class="modalDialog--wrapper">
                <div class="modalDialog--inner">
                    <a href="#close" title="Close" class="button-white-circle modalDialog--close"></a>
                    <div class="modalDialog--content">
                        Your modal text goes here
                    </div>
                </div>
                <a href="#close" class="modalDialog--mask"></a>
            </div>
        </section>
    ```

3. To the modal shows up, your modal id needs to be the same as your link
    ```
        <a href="#modalDialog">Open Modal!</a>
        <section id="modalDialog" class="modalDialog" role="dialog" aria-labelledby="modal-label" aria-hidden="true">
            ..............
            ..........
            .......

    ```

4. That will match the target of your link with your modal. This is the css to do the magic modal appear
    ```
        .modalDialog:target {
          opacity: 1;
          pointer-events: auto;
        }
    ```

5. Your can have a modal mask also (but keep in mind that this is optional)
   But if you include that within your component, whenever you click outside of the modal you will close it, because now the target is different from your modal id.
    ```
       <a href="#close" class="modalDialog--mask"></a>

       :target .modalDialog--mask {
            opacity: 0.7;
        }
    ```