---
title: '방법: 모눈 간 크기 조정 속성 공유'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190342"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="59817-102">방법: 모눈 간 크기 조정 속성 공유</span><span class="sxs-lookup"><span data-stu-id="59817-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="59817-103">이 예제에서는 열 크기 조정 데이터를 공유 하는 방법을 보여 줍니다 및 간에 행 <xref:System.Windows.Controls.Grid> 일관 된 크기 조정 유지 하기 위해 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="59817-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59817-104">예제</span><span class="sxs-lookup"><span data-stu-id="59817-104">Example</span></span>  
 <span data-ttu-id="59817-105">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Grid> 부모의 자식 요소로 요소 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="59817-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="59817-106">합니다 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 연결 속성 <xref:System.Windows.Controls.Grid> 부모에서 정의 된 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="59817-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="59817-107">이 예제에서는 두 개를 사용 하 여 속성 값을 조작 <xref:System.Windows.Controls.Button> 요소; 부울 속성 값의 각 요소 하나 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59817-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="59817-108">경우는 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 속성 값으로 설정 됩니다 `true`의 각 열 또는 행 멤버는 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> 행 또는 열의 콘텐츠에 관계 없이 크기 조정 정보를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="59817-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="59817-109">...</span><span class="sxs-lookup"><span data-stu-id="59817-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="59817-110">다음 코드 숨김 예제에서는 메서드를 처리 하는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="59817-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="59817-111">이러한 메서드 호출의 결과 작성 하는 예제 <xref:System.Windows.Controls.TextBlock> 사용 하 여 관련 요소를 새 속성 값을 문자열로 출력 하는 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59817-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="59817-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="59817-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="59817-113">Panel 개요</span><span class="sxs-lookup"><span data-stu-id="59817-113">Panels Overview</span></span>](panels-overview.md)
