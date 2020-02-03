---
title: '방법: ToolStrip 컨트롤에 대 한 사용자 지정 렌더러 만들기 및 설정'
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
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743413"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정
<xref:System.Windows.Forms.ToolStrip> 컨트롤을 통해 테마와 스타일을 쉽게 지원할 수 있습니다. <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성 또는 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성 중 하나를 사용자 지정 렌더러에서 설정 하 여 사용자 지정 모양 및 동작 (모양 및 느낌)을 완벽 하 게 구현할 수 있습니다.  
  
 각 개별 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>또는 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 렌더러를 할당 하거나 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 속성을 사용 하 여 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>로 설정 하 여 모든 개체에 영향을 줄 수 있습니다.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 값이 `null`되지 않은 경우에만 <xref:System.Windows.Forms.ToolStripRenderMode.Custom> 반환 됩니다.  
  
### <a name="to-create-a-custom-renderer"></a>사용자 지정 렌더러를 만들려면  
  
1. <xref:System.Windows.Forms.ToolStripRenderer> 클래스를 확장 합니다.  
  
2. 적절 한를 재정의 하 여 원하는 사용자 지정 렌더링 *을* 구현 합니다. members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>사용자 지정 렌더러를 현재 렌더러에서 설정 하려면  
  
1. 한 <xref:System.Windows.Forms.ToolStrip>에 대 한 사용자 지정 렌더러를 설정 하려면 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러로 설정 합니다.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 또는 응용 프로그램에 포함 된 모든 <xref:System.Windows.Forms.ToolStrip> 클래스에 대 한 사용자 지정 렌더러를 설정 하려면 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러로 설정 하 고 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>로 설정 합니다.  
  
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
