FTCoreText
===

An open source Objective-C component that makes use of the CoreText framework to render static text content with a highly customisable markup syntax.

##Usage

1. Include the CoreText.framework to your project
2. `#import FTCoreTextView.h`
3. Create an instance of `FTCoreTextView`
4. Apply styles to the output by creating instances of `FTCoreTextStyle` before adding them to the view.

```
FTCoreTextStyle *coloredStyle = [defaultStyle copy];
coloredStyle.name:@"coloured";
coloredStyle.color = [UIColor redColor];
 ```
 which is rendered red with markup: 
 `<coloured>I'm red</coloured>`

5. Once styles are defined, apply to the view: 

`[ftCoreTextInstance addStyles:@[style1, style2, style3]];`

6. Finally, set the text:

`ftCoreTextInstance.text = [self [NSString stringWithContentsOfFile:[[NSBundle mainBundle] pathForResource:@"MyStaticContent" ofType:@"txt"] encoding:NSUTF8StringEncoding error:nil]];`

See the example in the repository for greater detail.

##Elements

Several interface element types are included for rendering lists, images and suchlike:

`someFTCoreTextStyleInstance.name = FTCoreTextTagDefault`  

Included:

-  `FTCoreTextTagDefault`: the default style applied to the text. 
-  `FTCoreTextTagPage`: Divide the text in pages. Markup: `<_page/>`
-  `FTCoreTextTagBullet`: define styles for bullets. Markup: `<_bullet>content</bullet>`.
- `FTCoreTextTagImage`: renders images. Markup: `<_image>imageNameOnBundle.extension</_image>`
- `FTCoreTextTagLink`: define style for links. Markup: `<_link>link_target|link - name</_link>`. See `FTCoreTextViewDelegate` for responding to touch.

##Notes

1. Use of the CoreText framework is available for iOS versions 3.2 and above.

2. Although FTCoreTextView uses a similar markup syntax to HTML, most of the properties defined in the HTML specification are unsupported.

##Contact

FTCoreText is developed by [FuerteInt](http://fuerteint.com). Please [drop us an email](mailto:open-source@fuerteint.com) to let us know you how you are using this component.

##License

Open Source Initiative OSI - The MIT License (MIT):Licensing [OSI Approved License] The MIT License (MIT)

Copyright (c) 2013 Fuerte International

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.