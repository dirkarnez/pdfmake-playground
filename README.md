[pdfmake-playground](https://dirkarnez.github.io/pdfmake-playground/)
=====================================================================
### API documentation
- [pdfmake](https://pdfmake.github.io/docs/)

### Notes
- [`pdfmake.0.2.10.min.js`](pdfmake.0.2.10.min.js) is built using client-side settings.
- May use [PDFKit](https://pdfkit.org/) directly for more low-level PDF generation - [bpampuch/pdfmake](https://github.com/bpampuch/pdfmake) is an abstraction on top of it
  - `pdfmake` has APIs for tables
- Standard fonts are not available / not recommended to use in client-side. Should use CDN fonts / own font files
- Use `data-*` attributes for data for PDF generation instead of using html-to-pdf PDF generation:
  - ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>Page Title</title>
      </head>
    <body>
    
    <div id="parent-container" data-child-selector=".child-item">
      <div class="child-item">Child 1</div>
      <div class="child-item">Child 2</div>
      <div class="child-item">Child 3</div>
      <p>This is not a child item</p>
    </div>
    
    <script>
    const parentContainer = document.getElementById('parent-container');
    const data = Array.from(parentContainer.querySelectorAll(parentContainer.dataset.childSelector)).map(item => item.innerText);
    
    console.log(data);
    </script>
    </body>
    </html>
    ```
### Templates
- [dirkarnez/pdfmake-templates](https://github.com/dirkarnez/pdfmake-templates)
