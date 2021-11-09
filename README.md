# Custom Icons

How to create an icon in 4 steps.

> :speech_balloon: **NOTE**
> 
> I should add a script to automate this process...

## 1. Find Inspiration

I used `%TestStandBin%\REngine.exe` as an inspiration. I extracted REngine.exe with 7-Zip and used `.rsrc\ICON` content as a base for my Inkscape project.

## 2. Draw an Icon

I used [Inkscape](https://inkscape.org/release) to draw a simple icon based on the [TestStand](https://www.ni.com/en-us/shop/electronic-test-instrumentation/application-software-for-electronic-test-and-instrumentation-category/what-is-teststand.html) icon. I used [Stick](https://fonts.google.com/specimen/Stick) font from Google Fonts for the title of the icon. You can open the `.\Project\CustomSeqEdit.svg` project in Inkscape and customize it as needed.

## 3. Generate Source Files for the Icon

I used Inkscape CLI (make sure to add Inkscape to the `%PATH%`). I also used some tips regarding size from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/uxguide/vis-icons). Here is what I used:
```console
inkscape -w 16 -h 16 -o 16.png CustomSeqEdit.svg
inkscape -w 48 -h 48 -o 48.png CustomSeqEdit.svg
inkscape -w 64 -h 64 -o 64.png CustomSeqEdit.svg
inkscape -w 256 -h 256 -o 256.png CustomSeqEdit.svg
```

## 4. Generate Icon

I used [ImageMagick](https://imagemagick.org/index.php) CLI:
```console
magick convert 16.png 48.png 64.png 256.png seqedit.ico
```
