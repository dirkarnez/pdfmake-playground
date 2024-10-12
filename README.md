[pdfmake-playground](https://dirkarnez.github.io/pdfmake-playground/)
=====================================================================
### API documentation
- [pdfmake](https://pdfmake.github.io/docs/)

### Notes
- [`pdfmake.0.2.10.min.js`](pdfmake.0.2.10.min.js) is built using client-side settings.
- May use [PDFKit](https://pdfkit.org/) directly for more low-level PDF generation - [bpampuch/pdfmake](https://github.com/bpampuch/pdfmake) is an abstraction on top of it
  - `pdfmake` has APIs for tables
- Standard fonts are not available / not recommended to use in client-side. Should use CDN fonts / own font files
  - [前端PDF下載 | pdfmake自訂中文字型（使用NotoSansTC） | by Adam You | Medium](https://medium.com/@upstairs0102/%E5%89%8D%E7%AB%AFpdf%E4%B8%8B%E8%BC%89-pdfmake%E8%87%AA%E8%A8%82%E4%B8%AD%E6%96%87%E5%AD%97%E5%9E%8B-%E4%BD%BF%E7%94%A8notosanstc-f07177731ac6)
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
