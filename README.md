This is simply a wrapper that ensures the content published via MailModo is sized to fit the viewport of the device on which it is viewed.

It expects an argument p that is obtained from mailmodo Campaigns > (click on desired campaign name) > (three dots menu) > Publish on Web

This displays a publish link, and it should be of the form https://pub.mailmodo.dev/p/1iXrJOS62s

The argument p is then updated in livecms (Umbraco, the main UniteTheUnion web site) to be the last part of that link (in this example it should be 1iXrJOS62s)

This should be updated every month as new campaigns are created to send the WVP Monthly newsletter.

You can also adjust the height h and width w as needed, to match the iframe in livecms.

Here is the dynamic content (that needs updating monthly) in the Umbraco CMS.

```html
<p style="max-width: 100%; overflow-x: hidden; margin: 0px auto; text-align: center">
    <span
        class="umb-embed-holder"
        data-embed-constrain="false"
        data-embed-height="2600"
        data-embed-url="https://unitetheunion.github.io/embed/wrapper.html?p=1iXrJOS62s"   <!-- UPDATE THIS LINE -->
        data-embed-width="700">
        <iframe
            title="Newsletter"
            allowfullscreen="allowfullscreen"
            scrolling="no"
            src="https://unitetheunion.github.io/embed/wrapper.html?p=1iXrJOS62s" <!-- UPDATE THIS LINE -->
            style="
                border: 0 !important;
                display: block !important;
                width: min(700px, 100vw) !important;
                max-width: none !important;
                height: auto !important;
                aspect-ratio: 700/2600 !important;
                margin: 0 auto !important;
            "></iframe>
    </span>
</p>
```
