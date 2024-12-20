#  octique

0.1.0

GitHub Octicons for Typst.

GitHub [ Octicons ](https://primer.style/foundations/icons/) for Typst.

##  Installation

    
    
    #import "@preview/octique:0.1.0": *
    

##  Usage

    
    
    // Returns an image for the given name.
    octique(name, color: rgb("#000000"), width: 1em, height: 1em)
    
    // Returns a boxed image for the given name.
    octique-inline(name, color: rgb("#000000"), width: 1em, height: 1em, baseline: 25%)
    
    // Returns an SVG text for the given name.
    octique-svg(name)
    

##  List of Available Icons

See also [ ` sample/sample.pdf `
](https://github.com/typst/packages/raw/main/packages/preview/octique/0.1.0/sample/sample.pdf)
.

Code  |  Icon   
---|---  
` #octique("accessibility-inset") ` |  ![accessibility-inset](https://github.com/0x6b/typst-octique/wiki/assets/accessibility-inset.svg)  
` #octique("accessibility") ` |  ![accessibility](https://github.com/0x6b/typst-octique/wiki/assets/accessibility.svg)  
` #octique("alert-fill") ` |  ![alert-fill](https://github.com/0x6b/typst-octique/wiki/assets/alert-fill.svg)  
` #octique("alert") ` |  ![alert](https://github.com/0x6b/typst-octique/wiki/assets/alert.svg)  
` #octique("apps") ` |  ![apps](https://github.com/0x6b/typst-octique/wiki/assets/apps.svg)  
` #octique("archive") ` |  ![archive](https://github.com/0x6b/typst-octique/wiki/assets/archive.svg)  
` #octique("arrow-both") ` |  ![arrow-both](https://github.com/0x6b/typst-octique/wiki/assets/arrow-both.svg)  
` #octique("arrow-down-left") ` |  ![arrow-down-left](https://github.com/0x6b/typst-octique/wiki/assets/arrow-down-left.svg)  
` #octique("arrow-down-right") ` |  ![arrow-down-right](https://github.com/0x6b/typst-octique/wiki/assets/arrow-down-right.svg)  
` #octique("arrow-down") ` |  ![arrow-down](https://github.com/0x6b/typst-octique/wiki/assets/arrow-down.svg)  
` #octique("arrow-left") ` |  ![arrow-left](https://github.com/0x6b/typst-octique/wiki/assets/arrow-left.svg)  
` #octique("arrow-right") ` |  ![arrow-right](https://github.com/0x6b/typst-octique/wiki/assets/arrow-right.svg)  
` #octique("arrow-switch") ` |  ![arrow-switch](https://github.com/0x6b/typst-octique/wiki/assets/arrow-switch.svg)  
` #octique("arrow-up-left") ` |  ![arrow-up-left](https://github.com/0x6b/typst-octique/wiki/assets/arrow-up-left.svg)  
` #octique("arrow-up-right") ` |  ![arrow-up-right](https://github.com/0x6b/typst-octique/wiki/assets/arrow-up-right.svg)  
` #octique("arrow-up") ` |  ![arrow-up](https://github.com/0x6b/typst-octique/wiki/assets/arrow-up.svg)  
` #octique("beaker") ` |  ![beaker](https://github.com/0x6b/typst-octique/wiki/assets/beaker.svg)  
` #octique("bell-fill") ` |  ![bell-fill](https://github.com/0x6b/typst-octique/wiki/assets/bell-fill.svg)  
` #octique("bell-slash") ` |  ![bell-slash](https://github.com/0x6b/typst-octique/wiki/assets/bell-slash.svg)  
` #octique("bell") ` |  ![bell](https://github.com/0x6b/typst-octique/wiki/assets/bell.svg)  
` #octique("blocked") ` |  ![blocked](https://github.com/0x6b/typst-octique/wiki/assets/blocked.svg)  
` #octique("bold") ` |  ![bold](https://github.com/0x6b/typst-octique/wiki/assets/bold.svg)  
` #octique("book") ` |  ![book](https://github.com/0x6b/typst-octique/wiki/assets/book.svg)  
` #octique("bookmark-slash") ` |  ![bookmark-slash](https://github.com/0x6b/typst-octique/wiki/assets/bookmark-slash.svg)  
` #octique("bookmark") ` |  ![bookmark](https://github.com/0x6b/typst-octique/wiki/assets/bookmark.svg)  
` #octique("briefcase") ` |  ![briefcase](https://github.com/0x6b/typst-octique/wiki/assets/briefcase.svg)  
` #octique("broadcast") ` |  ![broadcast](https://github.com/0x6b/typst-octique/wiki/assets/broadcast.svg)  
` #octique("browser") ` |  ![browser](https://github.com/0x6b/typst-octique/wiki/assets/browser.svg)  
` #octique("bug") ` |  ![bug](https://github.com/0x6b/typst-octique/wiki/assets/bug.svg)  
` #octique("cache") ` |  ![cache](https://github.com/0x6b/typst-octique/wiki/assets/cache.svg)  
` #octique("calendar") ` |  ![calendar](https://github.com/0x6b/typst-octique/wiki/assets/calendar.svg)  
` #octique("check-circle-fill") ` |  ![check-circle-fill](https://github.com/0x6b/typst-octique/wiki/assets/check-circle-fill.svg)  
` #octique("check-circle") ` |  ![check-circle](https://github.com/0x6b/typst-octique/wiki/assets/check-circle.svg)  
` #octique("check") ` |  ![check](https://github.com/0x6b/typst-octique/wiki/assets/check.svg)  
` #octique("checkbox") ` |  ![checkbox](https://github.com/0x6b/typst-octique/wiki/assets/checkbox.svg)  
` #octique("checklist") ` |  ![checklist](https://github.com/0x6b/typst-octique/wiki/assets/checklist.svg)  
` #octique("chevron-down") ` |  ![chevron-down](https://github.com/0x6b/typst-octique/wiki/assets/chevron-down.svg)  
` #octique("chevron-left") ` |  ![chevron-left](https://github.com/0x6b/typst-octique/wiki/assets/chevron-left.svg)  
` #octique("chevron-right") ` |  ![chevron-right](https://github.com/0x6b/typst-octique/wiki/assets/chevron-right.svg)  
` #octique("chevron-up") ` |  ![chevron-up](https://github.com/0x6b/typst-octique/wiki/assets/chevron-up.svg)  
` #octique("circle-slash") ` |  ![circle-slash](https://github.com/0x6b/typst-octique/wiki/assets/circle-slash.svg)  
` #octique("circle") ` |  ![circle](https://github.com/0x6b/typst-octique/wiki/assets/circle.svg)  
` #octique("clock-fill") ` |  ![clock-fill](https://github.com/0x6b/typst-octique/wiki/assets/clock-fill.svg)  
` #octique("clock") ` |  ![clock](https://github.com/0x6b/typst-octique/wiki/assets/clock.svg)  
` #octique("cloud-offline") ` |  ![cloud-offline](https://github.com/0x6b/typst-octique/wiki/assets/cloud-offline.svg)  
` #octique("cloud") ` |  ![cloud](https://github.com/0x6b/typst-octique/wiki/assets/cloud.svg)  
` #octique("code-of-conduct") ` |  ![code-of-conduct](https://github.com/0x6b/typst-octique/wiki/assets/code-of-conduct.svg)  
` #octique("code-review") ` |  ![code-review](https://github.com/0x6b/typst-octique/wiki/assets/code-review.svg)  
` #octique("code") ` |  ![code](https://github.com/0x6b/typst-octique/wiki/assets/code.svg)  
` #octique("code-square") ` |  ![code-square](https://github.com/0x6b/typst-octique/wiki/assets/code-square.svg)  
` #octique("codescan-checkmark") ` |  ![codescan-checkmark](https://github.com/0x6b/typst-octique/wiki/assets/codescan-checkmark.svg)  
` #octique("codescan") ` |  ![codescan](https://github.com/0x6b/typst-octique/wiki/assets/codescan.svg)  
` #octique("codespaces") ` |  ![codespaces](https://github.com/0x6b/typst-octique/wiki/assets/codespaces.svg)  
` #octique("columns") ` |  ![columns](https://github.com/0x6b/typst-octique/wiki/assets/columns.svg)  
` #octique("command-palette") ` |  ![command-palette](https://github.com/0x6b/typst-octique/wiki/assets/command-palette.svg)  
` #octique("comment-discussion") ` |  ![comment-discussion](https://github.com/0x6b/typst-octique/wiki/assets/comment-discussion.svg)  
` #octique("comment") ` |  ![comment](https://github.com/0x6b/typst-octique/wiki/assets/comment.svg)  
` #octique("container") ` |  ![container](https://github.com/0x6b/typst-octique/wiki/assets/container.svg)  
` #octique("copilot-error") ` |  ![copilot-error](https://github.com/0x6b/typst-octique/wiki/assets/copilot-error.svg)  
` #octique("copilot") ` |  ![copilot](https://github.com/0x6b/typst-octique/wiki/assets/copilot.svg)  
` #octique("copilot-warning") ` |  ![copilot-warning](https://github.com/0x6b/typst-octique/wiki/assets/copilot-warning.svg)  
` #octique("copy") ` |  ![copy](https://github.com/0x6b/typst-octique/wiki/assets/copy.svg)  
` #octique("cpu") ` |  ![cpu](https://github.com/0x6b/typst-octique/wiki/assets/cpu.svg)  
` #octique("credit-card") ` |  ![credit-card](https://github.com/0x6b/typst-octique/wiki/assets/credit-card.svg)  
` #octique("cross-reference") ` |  ![cross-reference](https://github.com/0x6b/typst-octique/wiki/assets/cross-reference.svg)  
` #octique("dash") ` |  ![dash](https://github.com/0x6b/typst-octique/wiki/assets/dash.svg)  
` #octique("database") ` |  ![database](https://github.com/0x6b/typst-octique/wiki/assets/database.svg)  
` #octique("dependabot") ` |  ![dependabot](https://github.com/0x6b/typst-octique/wiki/assets/dependabot.svg)  
` #octique("desktop-download") ` |  ![desktop-download](https://github.com/0x6b/typst-octique/wiki/assets/desktop-download.svg)  
` #octique("device-camera") ` |  ![device-camera](https://github.com/0x6b/typst-octique/wiki/assets/device-camera.svg)  
` #octique("device-camera-video") ` |  ![device-camera-video](https://github.com/0x6b/typst-octique/wiki/assets/device-camera-video.svg)  
` #octique("device-desktop") ` |  ![device-desktop](https://github.com/0x6b/typst-octique/wiki/assets/device-desktop.svg)  
` #octique("device-mobile") ` |  ![device-mobile](https://github.com/0x6b/typst-octique/wiki/assets/device-mobile.svg)  
` #octique("devices") ` |  ![devices](https://github.com/0x6b/typst-octique/wiki/assets/devices.svg)  
` #octique("diamond") ` |  ![diamond](https://github.com/0x6b/typst-octique/wiki/assets/diamond.svg)  
` #octique("diff-added") ` |  ![diff-added](https://github.com/0x6b/typst-octique/wiki/assets/diff-added.svg)  
` #octique("diff-ignored") ` |  ![diff-ignored](https://github.com/0x6b/typst-octique/wiki/assets/diff-ignored.svg)  
` #octique("diff-modified") ` |  ![diff-modified](https://github.com/0x6b/typst-octique/wiki/assets/diff-modified.svg)  
` #octique("diff-removed") ` |  ![diff-removed](https://github.com/0x6b/typst-octique/wiki/assets/diff-removed.svg)  
` #octique("diff-renamed") ` |  ![diff-renamed](https://github.com/0x6b/typst-octique/wiki/assets/diff-renamed.svg)  
` #octique("diff") ` |  ![diff](https://github.com/0x6b/typst-octique/wiki/assets/diff.svg)  
` #octique("discussion-closed") ` |  ![discussion-closed](https://github.com/0x6b/typst-octique/wiki/assets/discussion-closed.svg)  
` #octique("discussion-duplicate") ` |  ![discussion-duplicate](https://github.com/0x6b/typst-octique/wiki/assets/discussion-duplicate.svg)  
` #octique("discussion-outdated") ` |  ![discussion-outdated](https://github.com/0x6b/typst-octique/wiki/assets/discussion-outdated.svg)  
` #octique("dot-fill") ` |  ![dot-fill](https://github.com/0x6b/typst-octique/wiki/assets/dot-fill.svg)  
` #octique("dot") ` |  ![dot](https://github.com/0x6b/typst-octique/wiki/assets/dot.svg)  
` #octique("download") ` |  ![download](https://github.com/0x6b/typst-octique/wiki/assets/download.svg)  
` #octique("duplicate") ` |  ![duplicate](https://github.com/0x6b/typst-octique/wiki/assets/duplicate.svg)  
` #octique("ellipsis") ` |  ![ellipsis](https://github.com/0x6b/typst-octique/wiki/assets/ellipsis.svg)  
` #octique("eye-closed") ` |  ![eye-closed](https://github.com/0x6b/typst-octique/wiki/assets/eye-closed.svg)  
` #octique("eye") ` |  ![eye](https://github.com/0x6b/typst-octique/wiki/assets/eye.svg)  
` #octique("feed-discussion") ` |  ![feed-discussion](https://github.com/0x6b/typst-octique/wiki/assets/feed-discussion.svg)  
` #octique("feed-forked") ` |  ![feed-forked](https://github.com/0x6b/typst-octique/wiki/assets/feed-forked.svg)  
` #octique("feed-heart") ` |  ![feed-heart](https://github.com/0x6b/typst-octique/wiki/assets/feed-heart.svg)  
` #octique("feed-issue-closed") ` |  ![feed-issue-closed](https://github.com/0x6b/typst-octique/wiki/assets/feed-issue-closed.svg)  
` #octique("feed-issue-draft") ` |  ![feed-issue-draft](https://github.com/0x6b/typst-octique/wiki/assets/feed-issue-draft.svg)  
` #octique("feed-issue-open") ` |  ![feed-issue-open](https://github.com/0x6b/typst-octique/wiki/assets/feed-issue-open.svg)  
` #octique("feed-issue-reopen") ` |  ![feed-issue-reopen](https://github.com/0x6b/typst-octique/wiki/assets/feed-issue-reopen.svg)  
` #octique("feed-merged") ` |  ![feed-merged](https://github.com/0x6b/typst-octique/wiki/assets/feed-merged.svg)  
` #octique("feed-person") ` |  ![feed-person](https://github.com/0x6b/typst-octique/wiki/assets/feed-person.svg)  
` #octique("feed-plus") ` |  ![feed-plus](https://github.com/0x6b/typst-octique/wiki/assets/feed-plus.svg)  
` #octique("feed-public") ` |  ![feed-public](https://github.com/0x6b/typst-octique/wiki/assets/feed-public.svg)  
` #octique("feed-pull-request-closed") ` |  ![feed-pull-request-closed](https://github.com/0x6b/typst-octique/wiki/assets/feed-pull-request-closed.svg)  
` #octique("feed-pull-request-draft") ` |  ![feed-pull-request-draft](https://github.com/0x6b/typst-octique/wiki/assets/feed-pull-request-draft.svg)  
` #octique("feed-pull-request-open") ` |  ![feed-pull-request-open](https://github.com/0x6b/typst-octique/wiki/assets/feed-pull-request-open.svg)  
` #octique("feed-repo") ` |  ![feed-repo](https://github.com/0x6b/typst-octique/wiki/assets/feed-repo.svg)  
` #octique("feed-rocket") ` |  ![feed-rocket](https://github.com/0x6b/typst-octique/wiki/assets/feed-rocket.svg)  
` #octique("feed-star") ` |  ![feed-star](https://github.com/0x6b/typst-octique/wiki/assets/feed-star.svg)  
` #octique("feed-tag") ` |  ![feed-tag](https://github.com/0x6b/typst-octique/wiki/assets/feed-tag.svg)  
` #octique("feed-trophy") ` |  ![feed-trophy](https://github.com/0x6b/typst-octique/wiki/assets/feed-trophy.svg)  
` #octique("file-added") ` |  ![file-added](https://github.com/0x6b/typst-octique/wiki/assets/file-added.svg)  
` #octique("file-badge") ` |  ![file-badge](https://github.com/0x6b/typst-octique/wiki/assets/file-badge.svg)  
` #octique("file-binary") ` |  ![file-binary](https://github.com/0x6b/typst-octique/wiki/assets/file-binary.svg)  
` #octique("file-code") ` |  ![file-code](https://github.com/0x6b/typst-octique/wiki/assets/file-code.svg)  
` #octique("file-diff") ` |  ![file-diff](https://github.com/0x6b/typst-octique/wiki/assets/file-diff.svg)  
` #octique("file-directory-fill") ` |  ![file-directory-fill](https://github.com/0x6b/typst-octique/wiki/assets/file-directory-fill.svg)  
` #octique("file-directory-open-fill") ` |  ![file-directory-open-fill](https://github.com/0x6b/typst-octique/wiki/assets/file-directory-open-fill.svg)  
` #octique("file-directory") ` |  ![file-directory](https://github.com/0x6b/typst-octique/wiki/assets/file-directory.svg)  
` #octique("file-directory-symlink") ` |  ![file-directory-symlink](https://github.com/0x6b/typst-octique/wiki/assets/file-directory-symlink.svg)  
` #octique("file-moved") ` |  ![file-moved](https://github.com/0x6b/typst-octique/wiki/assets/file-moved.svg)  
` #octique("file-removed") ` |  ![file-removed](https://github.com/0x6b/typst-octique/wiki/assets/file-removed.svg)  
` #octique("file") ` |  ![file](https://github.com/0x6b/typst-octique/wiki/assets/file.svg)  
` #octique("file-submodule") ` |  ![file-submodule](https://github.com/0x6b/typst-octique/wiki/assets/file-submodule.svg)  
` #octique("file-symlink-file") ` |  ![file-symlink-file](https://github.com/0x6b/typst-octique/wiki/assets/file-symlink-file.svg)  
` #octique("file-zip") ` |  ![file-zip](https://github.com/0x6b/typst-octique/wiki/assets/file-zip.svg)  
` #octique("filter") ` |  ![filter](https://github.com/0x6b/typst-octique/wiki/assets/filter.svg)  
` #octique("fiscal-host") ` |  ![fiscal-host](https://github.com/0x6b/typst-octique/wiki/assets/fiscal-host.svg)  
` #octique("flame") ` |  ![flame](https://github.com/0x6b/typst-octique/wiki/assets/flame.svg)  
` #octique("fold-down") ` |  ![fold-down](https://github.com/0x6b/typst-octique/wiki/assets/fold-down.svg)  
` #octique("fold") ` |  ![fold](https://github.com/0x6b/typst-octique/wiki/assets/fold.svg)  
` #octique("fold-up") ` |  ![fold-up](https://github.com/0x6b/typst-octique/wiki/assets/fold-up.svg)  
` #octique("gear") ` |  ![gear](https://github.com/0x6b/typst-octique/wiki/assets/gear.svg)  
` #octique("gift") ` |  ![gift](https://github.com/0x6b/typst-octique/wiki/assets/gift.svg)  
` #octique("git-branch") ` |  ![git-branch](https://github.com/0x6b/typst-octique/wiki/assets/git-branch.svg)  
` #octique("git-commit") ` |  ![git-commit](https://github.com/0x6b/typst-octique/wiki/assets/git-commit.svg)  
` #octique("git-compare") ` |  ![git-compare](https://github.com/0x6b/typst-octique/wiki/assets/git-compare.svg)  
` #octique("git-merge-queue") ` |  ![git-merge-queue](https://github.com/0x6b/typst-octique/wiki/assets/git-merge-queue.svg)  
` #octique("git-merge") ` |  ![git-merge](https://github.com/0x6b/typst-octique/wiki/assets/git-merge.svg)  
` #octique("git-pull-request-closed") ` |  ![git-pull-request-closed](https://github.com/0x6b/typst-octique/wiki/assets/git-pull-request-closed.svg)  
` #octique("git-pull-request-draft") ` |  ![git-pull-request-draft](https://github.com/0x6b/typst-octique/wiki/assets/git-pull-request-draft.svg)  
` #octique("git-pull-request") ` |  ![git-pull-request](https://github.com/0x6b/typst-octique/wiki/assets/git-pull-request.svg)  
` #octique("globe") ` |  ![globe](https://github.com/0x6b/typst-octique/wiki/assets/globe.svg)  
` #octique("goal") ` |  ![goal](https://github.com/0x6b/typst-octique/wiki/assets/goal.svg)  
` #octique("grabber") ` |  ![grabber](https://github.com/0x6b/typst-octique/wiki/assets/grabber.svg)  
` #octique("graph") ` |  ![graph](https://github.com/0x6b/typst-octique/wiki/assets/graph.svg)  
` #octique("hash") ` |  ![hash](https://github.com/0x6b/typst-octique/wiki/assets/hash.svg)  
` #octique("heading") ` |  ![heading](https://github.com/0x6b/typst-octique/wiki/assets/heading.svg)  
` #octique("heart-fill") ` |  ![heart-fill](https://github.com/0x6b/typst-octique/wiki/assets/heart-fill.svg)  
` #octique("heart") ` |  ![heart](https://github.com/0x6b/typst-octique/wiki/assets/heart.svg)  
` #octique("history") ` |  ![history](https://github.com/0x6b/typst-octique/wiki/assets/history.svg)  
` #octique("home") ` |  ![home](https://github.com/0x6b/typst-octique/wiki/assets/home.svg)  
` #octique("horizontal-rule") ` |  ![horizontal-rule](https://github.com/0x6b/typst-octique/wiki/assets/horizontal-rule.svg)  
` #octique("hourglass") ` |  ![hourglass](https://github.com/0x6b/typst-octique/wiki/assets/hourglass.svg)  
` #octique("hubot") ` |  ![hubot](https://github.com/0x6b/typst-octique/wiki/assets/hubot.svg)  
` #octique("id-badge") ` |  ![id-badge](https://github.com/0x6b/typst-octique/wiki/assets/id-badge.svg)  
` #octique("image") ` |  ![image](https://github.com/0x6b/typst-octique/wiki/assets/image.svg)  
` #octique("inbox") ` |  ![inbox](https://github.com/0x6b/typst-octique/wiki/assets/inbox.svg)  
` #octique("infinity") ` |  ![infinity](https://github.com/0x6b/typst-octique/wiki/assets/infinity.svg)  
` #octique("info") ` |  ![info](https://github.com/0x6b/typst-octique/wiki/assets/info.svg)  
` #octique("issue-closed") ` |  ![issue-closed](https://github.com/0x6b/typst-octique/wiki/assets/issue-closed.svg)  
` #octique("issue-draft") ` |  ![issue-draft](https://github.com/0x6b/typst-octique/wiki/assets/issue-draft.svg)  
` #octique("issue-opened") ` |  ![issue-opened](https://github.com/0x6b/typst-octique/wiki/assets/issue-opened.svg)  
` #octique("issue-reopened") ` |  ![issue-reopened](https://github.com/0x6b/typst-octique/wiki/assets/issue-reopened.svg)  
` #octique("issue-tracked-by") ` |  ![issue-tracked-by](https://github.com/0x6b/typst-octique/wiki/assets/issue-tracked-by.svg)  
` #octique("issue-tracks") ` |  ![issue-tracks](https://github.com/0x6b/typst-octique/wiki/assets/issue-tracks.svg)  
` #octique("italic") ` |  ![italic](https://github.com/0x6b/typst-octique/wiki/assets/italic.svg)  
` #octique("iterations") ` |  ![iterations](https://github.com/0x6b/typst-octique/wiki/assets/iterations.svg)  
` #octique("kebab-horizontal") ` |  ![kebab-horizontal](https://github.com/0x6b/typst-octique/wiki/assets/kebab-horizontal.svg)  
` #octique("key-asterisk") ` |  ![key-asterisk](https://github.com/0x6b/typst-octique/wiki/assets/key-asterisk.svg)  
` #octique("key") ` |  ![key](https://github.com/0x6b/typst-octique/wiki/assets/key.svg)  
` #octique("law") ` |  ![law](https://github.com/0x6b/typst-octique/wiki/assets/law.svg)  
` #octique("light-bulb") ` |  ![light-bulb](https://github.com/0x6b/typst-octique/wiki/assets/light-bulb.svg)  
` #octique("link-external") ` |  ![link-external](https://github.com/0x6b/typst-octique/wiki/assets/link-external.svg)  
` #octique("link") ` |  ![link](https://github.com/0x6b/typst-octique/wiki/assets/link.svg)  
` #octique("list-ordered") ` |  ![list-ordered](https://github.com/0x6b/typst-octique/wiki/assets/list-ordered.svg)  
` #octique("list-unordered") ` |  ![list-unordered](https://github.com/0x6b/typst-octique/wiki/assets/list-unordered.svg)  
` #octique("location") ` |  ![location](https://github.com/0x6b/typst-octique/wiki/assets/location.svg)  
` #octique("lock") ` |  ![lock](https://github.com/0x6b/typst-octique/wiki/assets/lock.svg)  
` #octique("log") ` |  ![log](https://github.com/0x6b/typst-octique/wiki/assets/log.svg)  
` #octique("logo-gist") ` |  ![logo-gist](https://github.com/0x6b/typst-octique/wiki/assets/logo-gist.svg)  
` #octique("logo-github") ` |  ![logo-github](https://github.com/0x6b/typst-octique/wiki/assets/logo-github.svg)  
` #octique("mail") ` |  ![mail](https://github.com/0x6b/typst-octique/wiki/assets/mail.svg)  
` #octique("mark-github") ` |  ![mark-github](https://github.com/0x6b/typst-octique/wiki/assets/mark-github.svg)  
` #octique("markdown") ` |  ![markdown](https://github.com/0x6b/typst-octique/wiki/assets/markdown.svg)  
` #octique("megaphone") ` |  ![megaphone](https://github.com/0x6b/typst-octique/wiki/assets/megaphone.svg)  
` #octique("mention") ` |  ![mention](https://github.com/0x6b/typst-octique/wiki/assets/mention.svg)  
` #octique("meter") ` |  ![meter](https://github.com/0x6b/typst-octique/wiki/assets/meter.svg)  
` #octique("milestone") ` |  ![milestone](https://github.com/0x6b/typst-octique/wiki/assets/milestone.svg)  
` #octique("mirror") ` |  ![mirror](https://github.com/0x6b/typst-octique/wiki/assets/mirror.svg)  
` #octique("moon") ` |  ![moon](https://github.com/0x6b/typst-octique/wiki/assets/moon.svg)  
` #octique("mortar-board") ` |  ![mortar-board](https://github.com/0x6b/typst-octique/wiki/assets/mortar-board.svg)  
` #octique("move-to-bottom") ` |  ![move-to-bottom](https://github.com/0x6b/typst-octique/wiki/assets/move-to-bottom.svg)  
` #octique("move-to-end") ` |  ![move-to-end](https://github.com/0x6b/typst-octique/wiki/assets/move-to-end.svg)  
` #octique("move-to-start") ` |  ![move-to-start](https://github.com/0x6b/typst-octique/wiki/assets/move-to-start.svg)  
` #octique("move-to-top") ` |  ![move-to-top](https://github.com/0x6b/typst-octique/wiki/assets/move-to-top.svg)  
` #octique("multi-select") ` |  ![multi-select](https://github.com/0x6b/typst-octique/wiki/assets/multi-select.svg)  
` #octique("mute") ` |  ![mute](https://github.com/0x6b/typst-octique/wiki/assets/mute.svg)  
` #octique("no-entry") ` |  ![no-entry](https://github.com/0x6b/typst-octique/wiki/assets/no-entry.svg)  
` #octique("north-star") ` |  ![north-star](https://github.com/0x6b/typst-octique/wiki/assets/north-star.svg)  
` #octique("note") ` |  ![note](https://github.com/0x6b/typst-octique/wiki/assets/note.svg)  
` #octique("number") ` |  ![number](https://github.com/0x6b/typst-octique/wiki/assets/number.svg)  
` #octique("organization") ` |  ![organization](https://github.com/0x6b/typst-octique/wiki/assets/organization.svg)  
` #octique("package-dependencies") ` |  ![package-dependencies](https://github.com/0x6b/typst-octique/wiki/assets/package-dependencies.svg)  
` #octique("package-dependents") ` |  ![package-dependents](https://github.com/0x6b/typst-octique/wiki/assets/package-dependents.svg)  
` #octique("package") ` |  ![package](https://github.com/0x6b/typst-octique/wiki/assets/package.svg)  
` #octique("paintbrush") ` |  ![paintbrush](https://github.com/0x6b/typst-octique/wiki/assets/paintbrush.svg)  
` #octique("paper-airplane") ` |  ![paper-airplane](https://github.com/0x6b/typst-octique/wiki/assets/paper-airplane.svg)  
` #octique("paperclip") ` |  ![paperclip](https://github.com/0x6b/typst-octique/wiki/assets/paperclip.svg)  
` #octique("passkey-fill") ` |  ![passkey-fill](https://github.com/0x6b/typst-octique/wiki/assets/passkey-fill.svg)  
` #octique("paste") ` |  ![paste](https://github.com/0x6b/typst-octique/wiki/assets/paste.svg)  
` #octique("pencil") ` |  ![pencil](https://github.com/0x6b/typst-octique/wiki/assets/pencil.svg)  
` #octique("people") ` |  ![people](https://github.com/0x6b/typst-octique/wiki/assets/people.svg)  
` #octique("person-add") ` |  ![person-add](https://github.com/0x6b/typst-octique/wiki/assets/person-add.svg)  
` #octique("person-fill") ` |  ![person-fill](https://github.com/0x6b/typst-octique/wiki/assets/person-fill.svg)  
` #octique("person") ` |  ![person](https://github.com/0x6b/typst-octique/wiki/assets/person.svg)  
` #octique("pin-slash") ` |  ![pin-slash](https://github.com/0x6b/typst-octique/wiki/assets/pin-slash.svg)  
` #octique("pin") ` |  ![pin](https://github.com/0x6b/typst-octique/wiki/assets/pin.svg)  
` #octique("pivot-column") ` |  ![pivot-column](https://github.com/0x6b/typst-octique/wiki/assets/pivot-column.svg)  
` #octique("play") ` |  ![play](https://github.com/0x6b/typst-octique/wiki/assets/play.svg)  
` #octique("plug") ` |  ![plug](https://github.com/0x6b/typst-octique/wiki/assets/plug.svg)  
` #octique("plus-circle") ` |  ![plus-circle](https://github.com/0x6b/typst-octique/wiki/assets/plus-circle.svg)  
` #octique("plus") ` |  ![plus](https://github.com/0x6b/typst-octique/wiki/assets/plus.svg)  
` #octique("project-roadmap") ` |  ![project-roadmap](https://github.com/0x6b/typst-octique/wiki/assets/project-roadmap.svg)  
` #octique("project") ` |  ![project](https://github.com/0x6b/typst-octique/wiki/assets/project.svg)  
` #octique("project-symlink") ` |  ![project-symlink](https://github.com/0x6b/typst-octique/wiki/assets/project-symlink.svg)  
` #octique("project-template") ` |  ![project-template](https://github.com/0x6b/typst-octique/wiki/assets/project-template.svg)  
` #octique("pulse") ` |  ![pulse](https://github.com/0x6b/typst-octique/wiki/assets/pulse.svg)  
` #octique("question") ` |  ![question](https://github.com/0x6b/typst-octique/wiki/assets/question.svg)  
` #octique("quote") ` |  ![quote](https://github.com/0x6b/typst-octique/wiki/assets/quote.svg)  
` #octique("read") ` |  ![read](https://github.com/0x6b/typst-octique/wiki/assets/read.svg)  
` #octique("redo") ` |  ![redo](https://github.com/0x6b/typst-octique/wiki/assets/redo.svg)  
` #octique("rel-file-path") ` |  ![rel-file-path](https://github.com/0x6b/typst-octique/wiki/assets/rel-file-path.svg)  
` #octique("reply") ` |  ![reply](https://github.com/0x6b/typst-octique/wiki/assets/reply.svg)  
` #octique("repo-clone") ` |  ![repo-clone](https://github.com/0x6b/typst-octique/wiki/assets/repo-clone.svg)  
` #octique("repo-deleted") ` |  ![repo-deleted](https://github.com/0x6b/typst-octique/wiki/assets/repo-deleted.svg)  
` #octique("repo-forked") ` |  ![repo-forked](https://github.com/0x6b/typst-octique/wiki/assets/repo-forked.svg)  
` #octique("repo-locked") ` |  ![repo-locked](https://github.com/0x6b/typst-octique/wiki/assets/repo-locked.svg)  
` #octique("repo-pull") ` |  ![repo-pull](https://github.com/0x6b/typst-octique/wiki/assets/repo-pull.svg)  
` #octique("repo-push") ` |  ![repo-push](https://github.com/0x6b/typst-octique/wiki/assets/repo-push.svg)  
` #octique("repo") ` |  ![repo](https://github.com/0x6b/typst-octique/wiki/assets/repo.svg)  
` #octique("repo-template") ` |  ![repo-template](https://github.com/0x6b/typst-octique/wiki/assets/repo-template.svg)  
` #octique("report") ` |  ![report](https://github.com/0x6b/typst-octique/wiki/assets/report.svg)  
` #octique("rocket") ` |  ![rocket](https://github.com/0x6b/typst-octique/wiki/assets/rocket.svg)  
` #octique("rows") ` |  ![rows](https://github.com/0x6b/typst-octique/wiki/assets/rows.svg)  
` #octique("rss") ` |  ![rss](https://github.com/0x6b/typst-octique/wiki/assets/rss.svg)  
` #octique("ruby") ` |  ![ruby](https://github.com/0x6b/typst-octique/wiki/assets/ruby.svg)  
` #octique("screen-full") ` |  ![screen-full](https://github.com/0x6b/typst-octique/wiki/assets/screen-full.svg)  
` #octique("screen-normal") ` |  ![screen-normal](https://github.com/0x6b/typst-octique/wiki/assets/screen-normal.svg)  
` #octique("search") ` |  ![search](https://github.com/0x6b/typst-octique/wiki/assets/search.svg)  
` #octique("server") ` |  ![server](https://github.com/0x6b/typst-octique/wiki/assets/server.svg)  
` #octique("share-android") ` |  ![share-android](https://github.com/0x6b/typst-octique/wiki/assets/share-android.svg)  
` #octique("share") ` |  ![share](https://github.com/0x6b/typst-octique/wiki/assets/share.svg)  
` #octique("shield-check") ` |  ![shield-check](https://github.com/0x6b/typst-octique/wiki/assets/shield-check.svg)  
` #octique("shield-lock") ` |  ![shield-lock](https://github.com/0x6b/typst-octique/wiki/assets/shield-lock.svg)  
` #octique("shield-slash") ` |  ![shield-slash](https://github.com/0x6b/typst-octique/wiki/assets/shield-slash.svg)  
` #octique("shield") ` |  ![shield](https://github.com/0x6b/typst-octique/wiki/assets/shield.svg)  
` #octique("shield-x") ` |  ![shield-x](https://github.com/0x6b/typst-octique/wiki/assets/shield-x.svg)  
` #octique("sidebar-collapse") ` |  ![sidebar-collapse](https://github.com/0x6b/typst-octique/wiki/assets/sidebar-collapse.svg)  
` #octique("sidebar-expand") ` |  ![sidebar-expand](https://github.com/0x6b/typst-octique/wiki/assets/sidebar-expand.svg)  
` #octique("sign-in") ` |  ![sign-in](https://github.com/0x6b/typst-octique/wiki/assets/sign-in.svg)  
` #octique("sign-out") ` |  ![sign-out](https://github.com/0x6b/typst-octique/wiki/assets/sign-out.svg)  
` #octique("single-select") ` |  ![single-select](https://github.com/0x6b/typst-octique/wiki/assets/single-select.svg)  
` #octique("skip-fill") ` |  ![skip-fill](https://github.com/0x6b/typst-octique/wiki/assets/skip-fill.svg)  
` #octique("skip") ` |  ![skip](https://github.com/0x6b/typst-octique/wiki/assets/skip.svg)  
` #octique("sliders") ` |  ![sliders](https://github.com/0x6b/typst-octique/wiki/assets/sliders.svg)  
` #octique("smiley") ` |  ![smiley](https://github.com/0x6b/typst-octique/wiki/assets/smiley.svg)  
` #octique("sort-asc") ` |  ![sort-asc](https://github.com/0x6b/typst-octique/wiki/assets/sort-asc.svg)  
` #octique("sort-desc") ` |  ![sort-desc](https://github.com/0x6b/typst-octique/wiki/assets/sort-desc.svg)  
` #octique("sparkle-fill") ` |  ![sparkle-fill](https://github.com/0x6b/typst-octique/wiki/assets/sparkle-fill.svg)  
` #octique("sponsor-tiers") ` |  ![sponsor-tiers](https://github.com/0x6b/typst-octique/wiki/assets/sponsor-tiers.svg)  
` #octique("square-fill") ` |  ![square-fill](https://github.com/0x6b/typst-octique/wiki/assets/square-fill.svg)  
` #octique("square") ` |  ![square](https://github.com/0x6b/typst-octique/wiki/assets/square.svg)  
` #octique("squirrel") ` |  ![squirrel](https://github.com/0x6b/typst-octique/wiki/assets/squirrel.svg)  
` #octique("stack") ` |  ![stack](https://github.com/0x6b/typst-octique/wiki/assets/stack.svg)  
` #octique("star-fill") ` |  ![star-fill](https://github.com/0x6b/typst-octique/wiki/assets/star-fill.svg)  
` #octique("star") ` |  ![star](https://github.com/0x6b/typst-octique/wiki/assets/star.svg)  
` #octique("stop") ` |  ![stop](https://github.com/0x6b/typst-octique/wiki/assets/stop.svg)  
` #octique("stopwatch") ` |  ![stopwatch](https://github.com/0x6b/typst-octique/wiki/assets/stopwatch.svg)  
` #octique("strikethrough") ` |  ![strikethrough](https://github.com/0x6b/typst-octique/wiki/assets/strikethrough.svg)  
` #octique("sun") ` |  ![sun](https://github.com/0x6b/typst-octique/wiki/assets/sun.svg)  
` #octique("sync") ` |  ![sync](https://github.com/0x6b/typst-octique/wiki/assets/sync.svg)  
` #octique("tab-external") ` |  ![tab-external](https://github.com/0x6b/typst-octique/wiki/assets/tab-external.svg)  
` #octique("table") ` |  ![table](https://github.com/0x6b/typst-octique/wiki/assets/table.svg)  
` #octique("tag") ` |  ![tag](https://github.com/0x6b/typst-octique/wiki/assets/tag.svg)  
` #octique("tasklist") ` |  ![tasklist](https://github.com/0x6b/typst-octique/wiki/assets/tasklist.svg)  
` #octique("telescope-fill") ` |  ![telescope-fill](https://github.com/0x6b/typst-octique/wiki/assets/telescope-fill.svg)  
` #octique("telescope") ` |  ![telescope](https://github.com/0x6b/typst-octique/wiki/assets/telescope.svg)  
` #octique("terminal") ` |  ![terminal](https://github.com/0x6b/typst-octique/wiki/assets/terminal.svg)  
` #octique("three-bars") ` |  ![three-bars](https://github.com/0x6b/typst-octique/wiki/assets/three-bars.svg)  
` #octique("thumbsdown") ` |  ![thumbsdown](https://github.com/0x6b/typst-octique/wiki/assets/thumbsdown.svg)  
` #octique("thumbsup") ` |  ![thumbsup](https://github.com/0x6b/typst-octique/wiki/assets/thumbsup.svg)  
` #octique("tools") ` |  ![tools](https://github.com/0x6b/typst-octique/wiki/assets/tools.svg)  
` #octique("tracked-by-closed-completed") ` |  ![tracked-by-closed-completed](https://github.com/0x6b/typst-octique/wiki/assets/tracked-by-closed-completed.svg)  
` #octique("tracked-by-closed-not-planned") ` |  ![tracked-by-closed-not-planned](https://github.com/0x6b/typst-octique/wiki/assets/tracked-by-closed-not-planned.svg)  
` #octique("trash") ` |  ![trash](https://github.com/0x6b/typst-octique/wiki/assets/trash.svg)  
` #octique("triangle-down") ` |  ![triangle-down](https://github.com/0x6b/typst-octique/wiki/assets/triangle-down.svg)  
` #octique("triangle-left") ` |  ![triangle-left](https://github.com/0x6b/typst-octique/wiki/assets/triangle-left.svg)  
` #octique("triangle-right") ` |  ![triangle-right](https://github.com/0x6b/typst-octique/wiki/assets/triangle-right.svg)  
` #octique("triangle-up") ` |  ![triangle-up](https://github.com/0x6b/typst-octique/wiki/assets/triangle-up.svg)  
` #octique("trophy") ` |  ![trophy](https://github.com/0x6b/typst-octique/wiki/assets/trophy.svg)  
` #octique("typography") ` |  ![typography](https://github.com/0x6b/typst-octique/wiki/assets/typography.svg)  
` #octique("undo") ` |  ![undo](https://github.com/0x6b/typst-octique/wiki/assets/undo.svg)  
` #octique("unfold") ` |  ![unfold](https://github.com/0x6b/typst-octique/wiki/assets/unfold.svg)  
` #octique("unlink") ` |  ![unlink](https://github.com/0x6b/typst-octique/wiki/assets/unlink.svg)  
` #octique("unlock") ` |  ![unlock](https://github.com/0x6b/typst-octique/wiki/assets/unlock.svg)  
` #octique("unmute") ` |  ![unmute](https://github.com/0x6b/typst-octique/wiki/assets/unmute.svg)  
` #octique("unread") ` |  ![unread](https://github.com/0x6b/typst-octique/wiki/assets/unread.svg)  
` #octique("unverified") ` |  ![unverified](https://github.com/0x6b/typst-octique/wiki/assets/unverified.svg)  
` #octique("upload") ` |  ![upload](https://github.com/0x6b/typst-octique/wiki/assets/upload.svg)  
` #octique("verified") ` |  ![verified](https://github.com/0x6b/typst-octique/wiki/assets/verified.svg)  
` #octique("versions") ` |  ![versions](https://github.com/0x6b/typst-octique/wiki/assets/versions.svg)  
` #octique("video") ` |  ![video](https://github.com/0x6b/typst-octique/wiki/assets/video.svg)  
` #octique("webhook") ` |  ![webhook](https://github.com/0x6b/typst-octique/wiki/assets/webhook.svg)  
` #octique("workflow") ` |  ![workflow](https://github.com/0x6b/typst-octique/wiki/assets/workflow.svg)  
` #octique("x-circle-fill") ` |  ![x-circle-fill](https://github.com/0x6b/typst-octique/wiki/assets/x-circle-fill.svg)  
` #octique("x-circle") ` |  ![x-circle](https://github.com/0x6b/typst-octique/wiki/assets/x-circle.svg)  
` #octique("x") ` |  ![x](https://github.com/0x6b/typst-octique/wiki/assets/x.svg)  
` #octique("zap") ` |  ![zap](https://github.com/0x6b/typst-octique/wiki/assets/zap.svg)  
` #octique("zoom-in") ` |  ![zoom-in](https://github.com/0x6b/typst-octique/wiki/assets/zoom-in.svg)  
` #octique("zoom-out") ` |  ![zoom-out](https://github.com/0x6b/typst-octique/wiki/assets/zoom-out.svg)  
  
##  License

MIT. See [ LICENSE
](https://github.com/typst/packages/raw/main/packages/preview/octique/0.1.0/LICENSE)
for detail.

Octicons are Â© GitHub, Inc. When using the GitHub logos, you should follow
the [ GitHub logo guidelines ](https://github.com/logos) .

###  How to add

Copy this into your project and use the import as  ` octique `

    
    
    #import "@preview/octique:0.1.0"

![Copy](/assets/icons/16-copy.svg)

Check the docs for  [ more information on how to import packages
](https://typst.app/docs/reference/scripting/#packages) .

###  About

Author  :

     0x6b 
License:

     MIT 
Current version:

     0.1.0 
Last updated:

     November 18, 2023 
First released:

     November 18, 2023 
Archive size:

     51.1 kB [ ![Size icon](/assets/icons/16-download.svg) ](https://packages.typst.org/preview/octique-0.1.0.tar.gz)
Repository:

     [ GitHub ](https://github.com/0x6b/typst-octique)

###  Where to report issues?

This  package  is a project of  0x6b  .  Report issues on  [ their repository
](https://github.com/0x6b/typst-octique) .  You can also try to ask for help
with this  package  on the  [ Forum ](https://forum.typst.app) .

Please report this  package  to the Typst team using the  [ contact form
](https://typst.app/contact) if you believe it is a safety hazard or infringes
upon your rights.

###  Version history

Version  |  Release Date   
---|---  
0.1.0  |  November 18, 2023   
  
Typst GmbH did not create this  package  and cannot guarantee correct
functionality of this  package  or compatibility with any version of the Typst
compiler or app.

