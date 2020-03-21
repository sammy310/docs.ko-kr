---
title: '방법: ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182398"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정
<xref:System.Windows.Forms.ToolStrip>컨트롤은 테마와 스타일에 대한 쉬운 지원을 제공합니다. <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성 또는 속성을 사용자 지정 렌더러로 설정하여 완전히 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 사용자 지정 모양과 동작(모양 및 느낌)을 얻을 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStrip>각 개인 에 렌더러를 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>할당할 <xref:System.Windows.Forms.StatusStrip> 수 있습니다. <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>의 <xref:System.Windows.Forms.ToolStripRenderMode.Custom> 값이 아닌 `null` <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 경우에만 반환합니다.  
  
### <a name="to-create-a-custom-renderer"></a>사용자 지정 렌더러를 만들려면  
  
1. 클래스를 <xref:System.Windows.Forms.ToolStripRenderer> 확장합니다.  
  
2. 적절한 *On을* 재정의하여 원하는 사용자 지정 렌더링을 구현합니다... members  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>사용자 지정 렌더러를 현재 렌더러로 설정하려면  
  
1. 사용자 지정 렌더러를 <xref:System.Windows.Forms.ToolStrip>하나에 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 설정하려면 속성을 사용자 지정 렌더러로 설정합니다.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 또는 응용 프로그램에 포함된 모든 <xref:System.Windows.Forms.ToolStrip> 클래스에 대한 사용자 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 지정 렌더러를 설정하려면 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>사용자 지정 렌더러로 설정하고 속성을 로 설정합니다.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
