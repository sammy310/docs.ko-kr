---
title: '방법: Windows Forms에서 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정'
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
ms.openlocfilehash: d8a85edf8c001b19191fdfd74d1f9ebdf87024ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195490"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>방법: Windows Forms에서 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정
<xref:System.Windows.Forms.ToolStrip> 컨트롤 테마 및 스타일을 손쉽게 지원을 제공합니다. 설정 하 여 완전 한 사용자 지정 모양 및 동작 (모양 및 느낌)을 구현할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성 또는 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러.  
  
 각 개인이 렌더러를 할당할 수 있습니다 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, 또는 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 속성을 설정 하 여 모든 개체에 영향을 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 반환 <xref:System.Windows.Forms.ToolStripRenderMode.Custom> 경우에만 값 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 아닙니다 `null`합니다.  
  
### <a name="to-create-a-custom-renderer"></a>사용자 지정 렌더러를 만들려면  
  
1.  확장 된 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다.  
  
2.  구현 원하는 사용자 지정 렌더링을 재정의 하 여 적절 한 *에서 하는 중...* 멤버  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>현재 렌더러를 사용자 지정 렌더러를 설정 하려면  
  
1.  하나에 대 한 사용자 지정 렌더러를 설정 하려면 <xref:System.Windows.Forms.ToolStrip>설정의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  모든 사용자 지정 렌더러를 설정 또는 <xref:System.Windows.Forms.ToolStrip> 응용 프로그램에 포함 된 클래스: 설정 된 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 설정 하 고는 사용자 지정 렌더러를 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>입니다.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
