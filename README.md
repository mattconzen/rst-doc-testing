This is a title in RST
======================

There\'s an RST cheatsheet available here:
<https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst>

I\'m going to try to include some examples from Consul, as well as
define some words as
[references](The%20word%20references%20can%20now%20be%20referenced%20throughout%20this%20doc%20as%20a%20canonical%20definition.)
which enable automatic inline definitions in our doc.

The cool thing about RST (aside from references, which are similar to
Markdown anchors but not quite the same) is that it supports
\'includes\'. We can embed snippets from another file directly in this
file, and it will render as if it was included inline.

So for Consul, if we wanted to reference the Catalog API[^1], we could
use an inline link or a citation reference like we could using Markdown.

However, we could also use an `include` directive which embeds some of
the text here directly:

``` {.go}
type CatalogService struct {
	ID                       string
	Node                     string
	Address                  string
	Datacenter               string
	TaggedAddresses          map[string]string
	NodeMeta                 map[string]string
	ServiceID                string
	ServiceName              string
	ServiceAddress           string
	ServiceTaggedAddresses   map[string]ServiceAddress
	ServiceTags              []string
	ServiceMeta              map[string]string
	ServicePort              int
	ServiceWeights           Weights
	ServiceEnableTagOverride bool
	ServiceProxy             *AgentServiceConnectProxyConfig
	CreateIndex              uint64
	Checks                   HealthChecks
	ModifyIndex              uint64
	Namespace                string `json:",omitempty"`
}

```

[^1]: <https://github.com/hashicorp/consul/blob/master/api/catalog.go>
