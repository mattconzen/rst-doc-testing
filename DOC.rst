This is a title in RST
======================

There's an RST cheatsheet available here: https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst

I'm going to try to include some examples from Consul, as well as define some words as `references`_ which enable automatic inline definitions in our doc.

.. _`references`: The word references can now be referenced throughout this doc as a canonical definition.

The cool thing about RST (aside from references, which are similar to Markdown anchors but not quite the same) is that it supports 'includes'. We can embed snippets from another file directly in this file, and it will render as if it was included inline.

So for Consul, if we wanted to reference the Catalog API [1]_, we could use an inline link or a citation reference like we could using Markdown.

However, we could also use an ``include`` directive which embeds some of the text here directly:

.. include:: consul/api/catalog.go
    :code: go
    :start-after: // rst-start CatalogService
    :end-before: // rst-end CatalogService

.. [1] https://github.com/hashicorp/consul/blob/master/api/catalog.go

