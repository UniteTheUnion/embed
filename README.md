This is simply a wrapper that ensures the content published via MailModo is sized to fit the viewport of the device on which it is viewed.

This is necessary because elevated security (!?) on the Umbraco site as of 2026-08 strips script tags, style tags, and we don't know what else from the "source" that is typed into a dynamic content element on an Umbraco page. I wish it were not so, but after failing to get it working directly in Umbraco, decided it is easier to work around than to row upstream. This wrapper is the workaround.

This wrapper expects an argument `p` that is obtained from `mailmodo Campaigns > (click on desired campaign name) > (three dots menu) > Publish on Web`

This displays a publish link, and it should be of the form `https://pub.mailmodo.dev/p/1iXrJOS62s` where the last part of this link is used as the value p (as shown below).

This should be updated every month as new campaigns are created to send the WVP Monthly newsletter.

You can also adjust the height h and width w as needed, to match the iframe in livecms, should this ever change. You will not normally need to adjust these values.

Here is the dynamic content in the Umbraco CMS that needs updating monthly, as new WVP Monthly emails are sent out.

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

Notice that the wrapper is exposed as a Github page on unitetheunion.github.io.
