# canvas-container

This project defines an interface to manage a paged drawing surface.  The _page_ can be an html canvas, pdf, svg, etc.

The need for this interface arises when rendering content onto a page.

1. When there is overflow, or when a page break is indicated in the source, the renderer needs to signal the start of a new page.
2. Links and anchors often need to be specified, such as for a table of contents, index, and/or hyperlinks.  These links must navigate to both internal and external locations.
3. Metadata for page, section, and container-name, such as title, author, chapter, and pageId need to be indicated.

Page numbers used as parameters are 1-based.

## Access
* page.getContainer
* page.setPageNumber(page, pageNumber)
* page.getPageNumber : pageNumber

## Metadata
* setAttribute(pageNumber | page, name, value)
* getAttribute(pageNumber | page, name) : value

## Page Managment
* addPage : page
* deletePage (pageNumber | page)
* insertPage (beforePageNumber | beforePage)
* movePage (targetPage, beforePageNumber | beforePage)
* deletePage (pageNumber | page)
* getPages : page[]

## Annotations (Links)
* beginAnnotation(type, url) : context
* endAnnotation(context)
* beginAnchor(name) : context
* endAnchor(context)
