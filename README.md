# Logos Maps catalog

Separate module catalog based on logos-co/logos-modules-release-base.
The source lives in the `submodules/logos-maps` git submodule. The two
module paths are `modules/osm_registry` and `modules/osm_distribution`.
The shared release workflow calls logos-co/logos-modules-release-action
for darwin-arm64 and linux-amd64. Packages are unsigned initially, matching
the empty trustedSigners in logos-repo.json.

After publishing the source revision and this fork, run **Release all map
modules** from Actions. Confirm both platform releases and the rolling
index release succeeded before distributing this installation URL:

https://raw.githubusercontent.com/anudit/logos-maps-catalog/main/logos-repo.json

Add that URL in Basecamp Settings → Package Repositories, refresh the
package manager and install OSM Distribution. The SDK is also independently
installable. Local test instructions are in the source's docs/LOCAL_TESTING.md.

For updates, publish the source commit, update this submodule pointer,
commit it, push, and rerun releases. The umbrella explicitly lists both
nested paths because upstream discovery expects one module per submodule.

This working tree is only a prepared catalog until actual releases succeed.
