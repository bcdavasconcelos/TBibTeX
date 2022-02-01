# TBibTex

You can use this template to manage your bibliographical entries.   

## Why BibTeX?

The idea behind using BibTeX is simple: with Pandoc, you can then convert it to pretty much any other format (e.g. DOCX, PPTX, HTML, CSL-JSON, LaTeX, PDF, and the list goes on). You could also use it directly with LaTeX, which affords some advantages, such as backlinks from the bibliography to the individual pages where an entry appears. But that is a subject for some other time…   

## Adding new entries

To add a new entry, simply create a new note and choose the appropriate prototype (e.g. Article, Book, or Chapter). Alternatively, you could just use the prototype Reference. For an entry to appear in the export, at the bare minimal you need to fill the "BibTexKey" attribute field (also known as the Citekey) and the "RefType" (depending on the prototypes, this one might already be filled for you).   

## Exporting

To export a BibTeX file, all you have to do is select the Content note and then hit File > Export Selected Note. There is no need to export all the notes in the file, as the content uses a preview template that will incorporate all of them. Alternatively, you could also just copy the text in the export pane and paste anywhere you need it.   

## Keeping notes under bib references

One advantage of using this system, is that you can keep your notes with your bibliographical entries. Just create as many notes as you want and place them as children of the main reference. If you don’t fill the special bib attributes (such as the BibTexKey), the export template will just ignore it. For more information on what will get exported, check the BibTeXitem export template.   

## Searching your entries

One of the motivations for making this template is that I prefer having my bibliography integrated with an app I already use all the time, such as Alfred, then keeping a dedicated app open in order to search my entries and cite them. This way, not only I get to search for an entry without the need to have Zotero or Bookends open, I also can choose whether I want to cite it, or open the corresponding Tbx note instead.   

## Alfred Workflow

To make this easier, I am already including the Alfred Workflow with the template. The Workflow will not search the Tbx project directly (I might include this option later). Instead, it will use a special version of the bib file that this template can also create. In this case, it is actually JSON and not BibTex: Alfred likes this format and the search works really fast.   

## BibTex and JSON Export

Again, to make things easier, I already included an Applescript in the Alfred Workflow which will update both your BibTeX and JSON files, exporting them to the chosen location. To update, simply activate the workflow and hit ⇧⏎. To export the files for the first time, open Alfred and type TBibTexExport.   

## Caveats

Should you decide to change the Tbx project file name, you will have to update the Alfred Workflow. Open Alfred’s configuration, go to the workflow and open the only item in red. Once you do that, you will see this:

```applescript
----------------------------------------
-------- Edit these variables --------
---------------------------------------
set theDocument to "TBibTex.tbx"
set theExportBibTeXFile to my fixHomePath("$HOME/.local/share/Pandoc/TbxRefs.bib")
set theExportedJSONFile to my fixHomePath("$HOME/.local/share/Pandoc/Refs_Alfred.json")
----------------------------------------
----------------------------------------	
```

Change the values according to your needs. Don’t worry about $HOME. The script will replace it with the actual first part of the path ("/Users/YourUserName/").


