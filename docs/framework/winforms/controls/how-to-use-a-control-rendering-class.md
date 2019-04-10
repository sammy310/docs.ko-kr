---
title: '방법: 컨트롤 렌더링 클래스 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: 7115c227cb24cf12a50073d0dc587524abf0cbb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163581"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="d2a70-102">방법: 컨트롤 렌더링 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="d2a70-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="d2a70-103">이 예제를 사용 하는 방법에 설명 합니다 <xref:System.Windows.Forms.ComboBoxRenderer> 드롭다운 화살표는 콤보 상자 컨트롤을 렌더링 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="d2a70-104">이 예제에서는 구성의 <xref:System.Windows.Forms.Control.OnPaint%2A> 간단한 사용자 지정 컨트롤의 메서드.</span><span class="sxs-lookup"><span data-stu-id="d2a70-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="d2a70-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> 속성 비주얼 스타일이 응용 프로그램 창의 클라이언트 영역에서 사용 되는지 여부를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="d2a70-106">비주얼 스타일을 활성화 하는 경우 해당 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> 메서드는 비주얼 스타일;를 사용 하 여 드롭다운 화살표를 렌더링 합니다이 고, 그렇지는 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> 메서드 클래식 Windows 스타일의 드롭다운 화살표를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2a70-107">예제</span><span class="sxs-lookup"><span data-stu-id="d2a70-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2a70-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d2a70-108">Compiling the Code</span></span>  
 <span data-ttu-id="d2a70-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-109">This example requires:</span></span>  
  
-   <span data-ttu-id="d2a70-110">파생 되는 사용자 지정 컨트롤을 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="d2a70-111"><xref:System.Windows.Forms.Form> 사용자 지정 컨트롤을 호스팅하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="d2a70-112">에 대 한 참조를 <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>를 <xref:System.Windows.Forms?displayProperty=nameWithType>, 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a70-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a70-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2a70-113">See also</span></span>

- [<span data-ttu-id="d2a70-114">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="d2a70-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
