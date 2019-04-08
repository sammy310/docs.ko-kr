---
title: '방법: 비주얼 스타일 요소 렌더링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 44218ee1f3879a3f9ac5a1e1b049c28a5463820e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099835"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="5bb80-102">방법: 비주얼 스타일 요소 렌더링</span><span class="sxs-lookup"><span data-stu-id="5bb80-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="5bb80-103">합니다 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 네임 스페이스는 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> Windows 사용자를 나타내는 개체 인터페이스 (UI) 요소 비주얼 스타일에서 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="5bb80-104">이 항목에서는 사용 하는 방법에 설명 합니다 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 렌더링 하는 클래스를 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 나타내는 **로그 오프** 및 **종료** 시작 메뉴의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="5bb80-105">비주얼 스타일 요소 렌더링</span><span class="sxs-lookup"><span data-stu-id="5bb80-105">To render a visual style element</span></span>  
  
1.  <span data-ttu-id="5bb80-106">만들기는 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 그릴 원하는 요소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="5bb80-107">사용 된 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> 메서드, <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> 생성자 비주얼 스타일을 사용할 수 없거나 정의 되어 있지 않은 경우 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  <span data-ttu-id="5bb80-108">호출을 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> 메서드를 요소는 렌더링는 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 현재 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5bb80-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5bb80-109">Compiling the Code</span></span>  
 <span data-ttu-id="5bb80-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-110">This example requires:</span></span>  
  
-   <span data-ttu-id="5bb80-111">파생 되는 사용자 지정 컨트롤을 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="5bb80-112"><xref:System.Windows.Forms.Form> 사용자 지정 컨트롤을 호스팅하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="5bb80-113">에 대 한 참조를 <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>를 <xref:System.Windows.Forms?displayProperty=nameWithType>, 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb80-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb80-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5bb80-114">See also</span></span>

- [<span data-ttu-id="5bb80-115">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="5bb80-115">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
