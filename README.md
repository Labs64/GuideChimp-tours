<a href="https://chrome.google.com/webstore/detail/guidechimp-chrome-extensi/afecedbgkfoijeligfjflidfddndnjng"><p align="center"><img src="https://io.labs64.com/GuideChimp/docs/img/guidechimp-logo-transparent-chrome.png" alt="GuideChimp Public Tours - Logo"></p></a>

<p align="center">
<a href="https://chrome.google.com/webstore/detail/guidechimp-chrome-extensi/afecedbgkfoijeligfjflidfddndnjng"><img src="https://img.shields.io/badge/chrome-web%20store-AB6543.svg" alt="GuideChimp @ Chrome Web Store"></a>
<a href="https://www.npmjs.com/package/guidechimp"><img src="https://img.shields.io/npm/v/guidechimp?color=AB6543&label=npm" alt="GuideChimp @ npm"></a>
<br>
<a href="https://github.com/Labs64/GuideChimp/wiki"><img src="https://img.shields.io/badge/docs-wiki-AB6543.svg" alt="Documentation"></a>
<a href="https://www.labs64.com/guidechimp/"><img src="https://img.shields.io/badge/website-labs64.com-AB6543.svg" alt="GuideChimp Website"></a>
<a href="https://github.com/Labs64/GuideChimp"><img src="https://img.shields.io/badge/core-GuideChimp-AB6543.svg" alt="GuideChimp Core"></a>
<a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-AB6543.svg" alt="MIT License"></a>
</p>

# GuideChimp Public Tours

This repository is an open collection of guided tours for popular websites. With the [GuideChimp Chrome Extension](https://chrome.google.com/webstore/detail/guidechimp-chrome-extensi/afecedbgkfoijeligfjflidfddndnjng) installed, a tour starts on any site that has one here. The sites don't need to change anything.

Tours exist today for GitLab, DocuSign, HubSpot, PandaDoc, Zoho CRM, Microsoft Outlook, SurveyMonkey, NetLicensing and Labs64. A tour for a site that has none yet is a good first contribution.

# How a tour file works

There is one JSON file per website, named after the host name, in `guidechimp/tours`, for example `app.hubspot.com.json`. The extension loads the file that matches the site you are visiting.

Each file maps a URL path pattern to the steps of the tour for that page. The pattern is a regular expression matched against the whole path. Each step is a [GuideChimp](https://github.com/Labs64/GuideChimp) step:

```json
{
    "/.*": [
        {
            "element": "#search",
            "title": "Search",
            "description": "Find anything from here.",
            "position": "bottom"
        }
    ]
}
```

- `element`: a CSS selector for the element to highlight. Leave it out for a message that isn't attached to an element.
- `title` and `description`: the text. The description may contain simple HTML such as links.
- `position`: where the tooltip goes, optional.

`_default.json` is shown on sites that have no tour yet. The [Wiki](https://github.com/Labs64/GuideChimp/wiki) describes all step options.

# How to contribute

1. Fork this repository.
2. Add or change a tour in `guidechimp/tours`. Check that the file is valid JSON and that every `element` selector exists on the live page.
3. Send a [pull request](https://github.com/Labs64/GuideChimp-tours/pulls). We review it and merge it.

Keep tours to public pages and public content. Don't include scripts or tracking in descriptions.

# Related projects

| Project | What it is | Where to get it |
|---|---|---|
| GuideChimp | The core library. | [npm](https://www.npmjs.com/package/guidechimp), [jsDelivr](https://www.jsdelivr.com/package/npm/guidechimp) |
| GuideChimp Plugins | Eight extra plugins, built into the `guidechimp` package under `dist/plugins`. | [Plugins wiki](https://github.com/Labs64/GuideChimp/wiki/Plugins) |
| GuideChimp Chrome Extension | Runs public tours on any website without changing it. | [Chrome Web Store](https://chrome.google.com/webstore/detail/guidechimp-chrome-extensi/afecedbgkfoijeligfjflidfddndnjng) |
| GuideChimp Editor | Chrome extension for authoring tours. Early stage. | In development |
| GuideChimp Public Tours | Community-maintained tours for popular websites (this repository). | [GitHub](https://github.com/Labs64/GuideChimp-tours) |

Also see the [GuideChimp website](https://www.labs64.com/guidechimp/) and the sample tour on [netlicensing.io](https://netlicensing.io).

# Bugs and feedback

For bugs, questions and discussions, please use [GitHub Issues](https://github.com/Labs64/GuideChimp/issues). To report a security problem, see [SECURITY.md](SECURITY.md).

GuideChimp is maintained by Labs64. [Contact](https://www.labs64.com/contact/) us for web app consulting, development and training, or to book a demo.

# License

The content in this repository is licensed under the [MIT license](LICENSE).
