
> 本文档主要记录平常碰到的一些小的技巧，包括但不限于Unity&编程等。

* 1. Debug 输出文件路径，并切可以点击等位
```csharp
    Debug.Log(path,AssetDataBase.LoadMainAssetAtPath(path) )
```

* 2. 编辑器下的进度条测试
```csharp
    [MenuItem("EditorTest/TestProcess")]
    private static void EditorProcess()
    {
        int index = 0;
        int total = 2000;
        EditorApplication.update = () =>
        {
            bool isCancel =
                EditorUtility.DisplayCancelableProgressBar("执行中...", $"描述文字...{index}", index / (float) total);
            index++;
            if (isCancel || index >= total)
            {
                EditorUtility.ClearProgressBar();
                Debug.Log("测试结束");
                EditorApplication.update = null;
            }
        };
    }  
```

* 3.获取编辑器Assets中选中的物体
```csharp
    selection.objects   //选中的物体
    selection.assetGUIDS // 选中物体的guid
    AssetDatabase.GUIDToAssetPath // 根据guid获取对应的路径  Assets/...
    AssetPathToGUID               // 根据路径获取对应的guid
```

* 4. 自定义EditorWindow



