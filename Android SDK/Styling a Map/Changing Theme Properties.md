---
title: "Changing Theme Properties"
excerpt: ""
---
It is possible to change the values of the properties inside current theme at runtime.

For a theme with an attribute like below,
[block:code]
{
  "codes": [
    {
      "code": "...\nglobal:\n\tshow_transit: false\n...",
      "language": "yaml"
    }
  ]
}
[/block]
 We can change the value of `show_transit` as below.
[block:code]
{
  "codes": [
    {
      "code": "// for path of the property, append scopes with a dot(\".\")\nval sceneUpdate = SceneUpdate(\"global.show_transit\", \"true\")\nmapfitMap.getMapOptions().updateScene(listOf(sceneUpdate))",
      "language": "kotlin",
      "name": "kotlin"
    },
    {
      "code": "// for path of the property, append scopes with a dot(\".\")\nSceneUpdate sceneUpdate = new SceneUpdate(\"global.show_transit\", \"true\");\n\nList<SceneUpdate> sceneUpdates = new ArrayList<>();\nsceneUpdates.add(sceneUpdate);\n\nmapfitMap.getMapOptions().updateScene(sceneUpdates);",
      "language": "java",
      "name": "java"
    }
  ]
}
[/block]
**Note:** Each call of `updateScene` will cause a scene load and if set, [OnMapThemeLoadListener](ref:onmapthemeloadlistener) will be triggered.