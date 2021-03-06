---
title: 如何：使用 WebBrowser 控件导航到 URL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: b6c1255fa17d91daaa73001fea04f26e73dba0ae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015831"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>如何：使用 WebBrowser 控件导航到 URL
下面的代码示例演示如何将<xref:System.Windows.Forms.WebBrowser>控件导航到特定的 URL。

 若要确定新文档完全加载的时间, 请处理<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件。 有关此事件的演示, 请参阅[如何:使用 WebBrowser 控件](how-to-print-with-a-webbrowser-control.md)打印。

## <a name="example"></a>示例

```vb
Me.webBrowser1.Navigate("http://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("http://www.microsoft.com");
```

## <a name="compiling-the-code"></a>编译代码
 此示例需要：

- 名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。

- 对 `System` 和 `System.Windows.Forms` 程序集的引用。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [WebBrowser 控件](webbrowser-control-windows-forms.md)
- [如何：使用 WebBrowser 控件进行打印](how-to-print-with-a-webbrowser-control.md)
