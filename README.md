Tesseract OCR iOS
=================

Tesseract OCR iOS is a Framework for iOS5+, also for armv7s.
<br />
<br />
It will help you to use OCR in a iOS project. Easy and fast.

Attach the project
=================

Add the framework "TesseractOCR.framework" (you can drag&drop it) from the <strong>Products</strong> folder in this repo, to your XCode Project under your project
<br />
If you are masochist :) you can generate your TesseractOCR.framework building the TesseractOCRAggregate target. 
<br />
<br />
Go to your project, click on the project and in the Build Settings tab add <code>-lstdc++</code> to all the "Other Linker Flags" keys.
<br />
Go to your project settings, and ensure that C++ Standard Library => Compiler Default. (thanks to https://github.com/trein)
<br />
Import the <code>tessdata</code> folder under the root of your project. It contains the "tessdata" files. You can add more tessdata files copyng them here.
<br />
Import the header in your classes writing <code>#import &lt;TesseractOCR/TesseractOCR.h&gt;</code>
<br />
Now you can use Tesseract class like explained here: https://github.com/ldiqual/tesseract-ios

ex. from https://github.com/ldiqual/tesseract-ios but using the <strong>"TesseractOCR.framework"</strong>
<pre><code>#import &lt;TesseractOCR/TesseractOCR.h&gt;

Tesseract* tesseract = [[Tesseract alloc] initWithDataPath:@"tessdata" language:@"<strong>eng</strong>"];
//language are used for recognition. Ex: eng. Tesseract will search for a eng.traineddata file in the dataPath directory. 
//eng.traineddata is in your "tessdata" folder.

[tesseract setVariableValue:@"0123456789" forKey:@"tessedit_char_whitelist"]; //limit search
[tesseract setImage:[UIImage imageNamed:@"image_sample.jpg"]]; //image to check
[tesseract recognize];

NSLog(@"%@", [tesseract recognizedText]);
</code></pre>

<br />
Set Tesseract variable key to value. See http://www.sk-spell.sk.cx/tesseract-ocr-en-variables for a complete (but not up-to-date) list.
<br />
For instance, use tessedit_char_whitelist to restrict characters to a specific set.

Dependencies
=================

Tesseract OCR iOS use UIKit, Foundation and CoreFoundation. They are already included in standard iOS Projects.

License
=================

Tesseract OCR iOS and TesseractOCR.framework are under MIT License.
<br />
Tesseract-ios, powered by ldiqual https://github.com/ldiqual/tesseract-ios, is under MIT License.
<br />
Tesseract, powered by Google http://code.google.com/p/tesseract-ocr/, is under Apache License.

Thanks
=================

Thanks to ldiqual for the good wrapper for Tesseract.

Author Infos
=================

Daniele Galiotto www.g8production.com

