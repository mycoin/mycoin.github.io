title: Icarus User Guide - Other Plugins
date: 2017-01-31
categories:
- Plugins
- Other
tags:
- Icarus User Guide
language: en
toc: true
plugins:
    animejs: true
    back_to_top: true
    cookie_consent:
        type: info
        theme: classic
        static: false
        position: bottom
        policyLink: 'https://www.cookiesandyou.com/'
    gallery: true
    google_analytics:
        tracking_id: UA-72437521-5
    mathjax: true
    outdated_browser: true
    progressbar: true
---

This article covers other plugins supported by Icarus 3.

<article class="message message-immersive is-primary">
<div class="message-body">
<i class="fas fa-globe-asia mr-2"></i>This article is also available in 
<a href="{% post_path zh-CN/Other-Plugins %}">简体中文</a>.
</div>
</article>

<!-- more -->

<article class="message message-immersive is-primary">
<div class="message-body">
<i class="fas fa-info-circle mr-2"></i>The following plugins are provided by
<a href="https://github.com/ppoffice/hexo-component-inferno">ppoffice/hexo-component-inferno</a>.
Please refer to it for a complete list of supported plugins and their configuration details.
</div>
</article>


## Gallery

**Installation Guide**

The gallery plugin of Icarus contains both [lightGallery](https://sachinchoolur.github.io/lightGallery/) and
[Justified Gallery](https://miromannino.github.io/Justified-Gallery/) extensions.
To enable it, set `plugins` > `gallery` to `true` in your theme configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    gallery: true
{% endcodeblock %}

Additionally, in order to use Justified Gallery, wrap your images with the `<div class="justified-gallery">`
and `</div>` HTML tag pair.
Also, if you are using Markdown syntax to include images, add additional empty lines between the HTML tags and
Markdown tags.
For example, the Markdown code of the gallery preview below is

{% codeblock "Justified-Gallery-Markdown.md" lang:markdown >folded %}
<div class="justified-gallery">

![Elephant](/hexo-theme-icarus/gallery/animals/elephant.jpeg)
![Dog](/hexo-theme-icarus/gallery/animals/dog.jpeg)
![Birds](/hexo-theme-icarus/gallery/animals/birds.jpeg)
![Fox](/hexo-theme-icarus/gallery/animals/fox.jpeg)
![Horse](/hexo-theme-icarus/gallery/animals/horse.jpeg)
![Leopard](/hexo-theme-icarus/gallery/animals/leopard.jpeg)

</div>
{% endcodeblock %}

Meanwhile, we can use pure HTML to create Justified Galleries as well.
In this case, we will not need the empty lines between HTML tags.

{% codeblock "Justified-Gallery-HTML.md" lang:html >folded %}
<div class="justified-gallery">
<img src="/hexo-theme-icarus/gallery/animals/elephant.jpeg" alt="Elephant" />
<img src="/hexo-theme-icarus/gallery/animals/dog.jpeg" alt="Dog" />
<img src="/hexo-theme-icarus/gallery/animals/birds.jpeg" alt="Birds" />
<img src="/hexo-theme-icarus/gallery/animals/fox.jpeg" alt="Fox" />
<img src="/hexo-theme-icarus/gallery/animals/horse.jpeg" alt="Horse" />
<img src="/hexo-theme-icarus/gallery/animals/leopard.jpeg" alt="Leopard" />
</div>
{% endcodeblock %}


**Preview**

Here is an image grid created by Justified Gallery.
You can also view the full image using lightGallery by clicking on any image.

<article class="message message-immersive is-primary">
<div class="message-body">
<i class="fas fa-info-circle mr-2"></i>The following photos come from <a href="https://www.pexels.com">pexel.com</a>
</div>
</article>

<div class="justified-gallery">

![Elephant](/hexo-theme-icarus/gallery/animals/elephant.jpeg)
![Dog](/hexo-theme-icarus/gallery/animals/dog.jpeg)
![Birds](/hexo-theme-icarus/gallery/animals/birds.jpeg)
![Fox](/hexo-theme-icarus/gallery/animals/fox.jpeg)
![Horse](/hexo-theme-icarus/gallery/animals/horse.jpeg)
![Leopard](/hexo-theme-icarus/gallery/animals/leopard.jpeg)

</div>


## KaTeX

**Installation Guide**

You can use the KaTeX plugin to render \\(\TeX\\) expressions.
To enable KaTeX, please set `plugins` > `katex` to `true` in your theme configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    katex: true
{% endcodeblock %}

Please also use `\\(` and `\\)` to wrap your inline expressions and `$$` or `\\[` and `\\]` pair to wrap 
block expressions.
For example,

{% codeblock Some-Post.md lang:markdown >folded %}
This is an inline expression: \\(ax^2+bx+c=0\\).

This is a block expression:
$$\displaystyle \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} = 
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} 
{1+\frac{e^{-8\pi}} {1+\cdots} } } }$$

This is another block expression:
\\[f(x) = \int_{-\infty}^\infty\hat f(\xi)e^{2 \pi i \xi x}d\xi\\]
{% endcodeblock %}

Sometimes your \\(\TeX\\) syntax will be mistaken as Markdown syntax, which will result in rendering error.
For instance, the following equation will not work since it contains more than one `_` (underscores), 
which are mistaken for the italic text when processed by the Markdown renderer:

{% codeblock Some-Post.md lang:tex %}
$$
\hat{x}_{k}=\hat{x}_{k}^{-}+K_{t}\left(y_{k}\right)
$$
{% endcodeblock %}

In this case, you can either escape every character that may cause confusion:

{% codeblock Some-Post.md lang:tex %}
$$
\hat{x}\_{k}=\hat{x}\_{k}^{-}+K\_{t}\left(y\_{k}\right)
$$
{% endcodeblock %}

or simply wrap the whole equation with an additional pair of HTML tags:

{% codeblock Some-Post.md lang:tex %}
<div>
$$
\hat{x}_{k}=\hat{x}_{k}^{-}+K_{t}\left(y_{k}\right)
$$
</div>
{% endcodeblock %}

## MathJax

**Installation Guide**

You can use MathJax to render \\(\TeX\\), MathML, or AsciiMath expressions.
To enable MathJax, please set `plugins` > `mathjax` to `true` in your theme configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    mathjax: true
{% endcodeblock %}

When using the \\(\TeX\\) syntax, please use `$` or `\\(` and `\\)` to wrap your inline expressions and
and `$$` or `\\[` and `\\]` pair to wrap block expressions.
You can also use \\(\LaTeX\\) environments directly.
For example,

{% codeblock Tex-Example.md lang:markdown >folded %}
This is an inline expression: \\(ax^2+bx+c=0\\). This is another inline expression: $ax^2+bx+c>0$.

This is a block expression:
$$\displaystyle \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} = 
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} 
{1+\frac{e^{-8\pi}} {1+\cdots} } } }$$

This is another block expression:
\\[f(x) = \int_{-\infty}^\infty\hat f(\xi)e^{2 \pi i \xi x}d\xi\\]

Or use \\(\LaTeX\\) environment:
\\begin{equation}
A =
\\begin{bmatrix}
  a & b \\\\
  c & c
\\end{bmatrix}
\\end{equation}
{% endcodeblock %}

Or you can use MathML syntax.
For example, 

{% codeblock MathML-Example.md lang:html >folded %}
When 
<math xmlns="http://www.w3.org/1998/Math/MathML">
    <mi>a</mi>
    <mo>≠</mo>
    <mn>0</mn>
</math>, 
there are two solutions to 
<math xmlns="http://www.w3.org/1998/Math/MathML">
    <mi>a</mi>
    <msup>
        <mi>x</mi>
        <mn>2</mn>
    </msup>
    <mo>+</mo>
    <mi>b</mi>
    <mi>x</mi>
    <mo>+</mo>
    <mi>c</mi>
    <mo>=</mo>
    <mn>0</mn>
</math> 
and they are
<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
    <mi>x</mi>
    <mo>=</mo>
    <mrow>
        <mfrac>
            <mrow>
                <mo>-</mo>
                <mi>b</mi>
                <mo>±</mo>
                <msqrt>
                    <msup>
                        <mi>b</mi>
                        <mn>2</mn>
                    </msup>
                    <mo>-</mo>
                    <mn>4</mn>
                    <mi>a</mi>
                    <mi>c</mi>
                </msqrt>
            </mrow>
            <mrow>
                <mn>2</mn>
                <mi>a</mi>
            </mrow>
        </mfrac>
    </mrow>
    <mtext>.</mtext>
</math>
{% endcodeblock %}

Similarly, you can also use AsciiMath supported by MathJax.
Expressions should be wrapped in <code>\\`</code> in this case.

{% codeblock AsciiMath-Example.md lang:markdown >folded %}
When \`a != 0\`, there are two solutions to \`ax^2 + bx + c = 0\` and they are <p style="text-align:center">\`x = (-b +- sqrt(b^2-4ac))/(2a)\`.</p>
{% endcodeblock %}

Sometimes your latex syntax will be mistaken as Markdown syntax, which will result in rendering error.
Please refer to the [KaTeX](#KaTeX) section for solutions to this.

**Preview(\\(\TeX\\) & \\(\LaTeX\\))**

This is an inline expression: \\(ax^2+bx+c=0\\). This is another inline expression: $ax^2+bx+c>0$.

This is a block expression:
$$\displaystyle \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} = 
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}} 
{1+\frac{e^{-8\pi}} {1+\cdots} } } }$$

This is another block expression:
\\[f(x) = \int_{-\infty}^\infty\hat f(\xi)e^{2 \pi i \xi x}d\xi\\]

Or use \\(\LaTeX\\) environment:
\\begin{equation}
A =
\\begin{bmatrix}
  a & b \\\\
  c & c
\\end{bmatrix}
\\end{equation}

**Preview(MathML)**

When 
<math xmlns="http://www.w3.org/1998/Math/MathML">
    <mi>a</mi>
    <mo>≠</mo>
    <mn>0</mn>
</math>, 
there are two solutions to 
<math xmlns="http://www.w3.org/1998/Math/MathML">
    <mi>a</mi>
    <msup>
        <mi>x</mi>
        <mn>2</mn>
    </msup>
    <mo>+</mo>
    <mi>b</mi>
    <mi>x</mi>
    <mo>+</mo>
    <mi>c</mi>
    <mo>=</mo>
    <mn>0</mn>
</math> 
and they are
<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
    <mi>x</mi>
    <mo>=</mo>
    <mrow>
        <mfrac>
            <mrow>
                <mo>-</mo>
                <mi>b</mi>
                <mo>±</mo>
                <msqrt>
                    <msup>
                        <mi>b</mi>
                        <mn>2</mn>
                    </msup>
                    <mo>-</mo>
                    <mn>4</mn>
                    <mi>a</mi>
                    <mi>c</mi>
                </msqrt>
            </mrow>
            <mrow>
                <mn>2</mn>
                <mi>a</mi>
            </mrow>
        </mfrac>
    </mrow>
    <mtext>.</mtext>
</math>

**Preview(AsciiMath)**

When \`a != 0\`, there are two solutions to \`ax^2 + bx + c = 0\` and they are <p style="text-align:center">\`x = (-b +- sqrt(b^2-4ac))/(2a)\`.</p>


## Cookie Consent

**Installation Guide**

You can show a cookie consent dialog to your visitor by enabling the Cookie Consent plugin.
Please refer to [Download Cookie Consent](https://www.osano.com/cookieconsent/download/) and 
[Documentation for the Cookie Consent plugin](https://www.osano.com/cookieconsent/documentation/about-cookie-consent/)
for details on each configuration setting.
You can also disable the cookie consent dialog by commenting out the configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    cookie_consent:
        # The compliance type. Can be "info", "opt-in", or "opt-out"
        type: info
        # Theme of the popup. Can be "block", "edgeless", or "classic"
        theme: edgeless
        # Whether the popup should stay static regardless of the page scrolls
        static: false
        # Where on the screen the consent popup should display
        position: bottom-left
        # URL to your site's cookie policy
        policyLink: 'https://www.cookiesandyou.com/'
{% endcodeblock %}


## Outdated Browser

**Installation Guide**

You can use the Outdated Browser plugin to detect outdated browsers used by
your site's visitors and remind them to upgrade their browsers.
To enable it, please set `plugins` > `outdated_browser` to `true` in your theme configurations.
Click [here](https://bestvpn.org/outdatedbrowser/en) to see a live preview of this plugin.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    outdated_browser: true
{% endcodeblock %}


## Page Loading Animations

**Installation Guide**

Page Loading Animations are enabled by Icarus by default.
To disable it, please set `plugins` > `animejs` to `false` in your theme configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    animejs: false
{% endcodeblock %}

Also, to disable the page loading progressbar, please set `plugins` > `progressbar` to `false` in 
your theme configurations.

{% codeblock _config.icarus.yml lang:yaml %}
plugins:
    progressbar: false
{% endcodeblock %}


<article class="message message-immersive is-warning">
<div class="message-body">
<i class="fas fa-question-circle mr-2"></i>Something wrong with this article? 
Click <a href="https://github.com/ppoffice/hexo-theme-icarus/edit/site/source/_posts/en/Other-Plugins.md">here</a> 
to submit your revision.
</div>
</article>
