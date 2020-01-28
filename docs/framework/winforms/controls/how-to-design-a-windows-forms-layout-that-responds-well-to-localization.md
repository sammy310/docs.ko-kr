---
title: 지역화 친화적인 레이아웃 디자인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 36ffd532b9f539107307144d25c8d9d5f8ba634a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743287"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="627a2-102">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="627a2-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="627a2-103">지역화할 준비가 된 폼을 만들면 국제 시장에서 개발 속도를 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="627a2-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 <xref:System.Windows.Forms.Control.Text%2A> 속성 값 변경 때문에 컨트롤 크기가 조정될 때 정상적으로 응답하는 레이아웃을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="627a2-105">예</span><span class="sxs-lookup"><span data-stu-id="627a2-105">Example</span></span>  
 <span data-ttu-id="627a2-106">이 폼에서는 표시된 문자열 값을 다른 언어로 번역할 때 비례하여 조정되는 레이아웃을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="627a2-107">이 번역 프로세스를 *지역화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="627a2-108">자세한 내용은 [지역화](../../../standard/globalization-localization/localization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="627a2-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="627a2-109">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="627a2-110">또한 [연습: 지역화를 위해 비율을 조정하는 레이아웃 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="627a2-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="627a2-111">추가 자료</span><span class="sxs-lookup"><span data-stu-id="627a2-111">Additional resources</span></span>

1. [<span data-ttu-id="627a2-112">방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기</span><span class="sxs-lookup"><span data-stu-id="627a2-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="627a2-113">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="627a2-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="627a2-114">방법: TableLayoutPanel 컨트롤에서 행과 열 확장</span><span class="sxs-lookup"><span data-stu-id="627a2-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="627a2-115">방법: TableLayoutPanel 컨트롤에서 열과 행 편집</span><span class="sxs-lookup"><span data-stu-id="627a2-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="627a2-116">연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="627a2-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="627a2-117">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="627a2-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="627a2-118">연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="627a2-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. <span data-ttu-id="627a2-119">[방법: AutoSize 속성과 TableLayoutPanel 컨트롤을 사용하여 Windows Forms 지역화 지원](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="627a2-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>  
  
9. <span data-ttu-id="627a2-120">[연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="627a2-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="627a2-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="627a2-121">Compiling the Code</span></span>  
 <span data-ttu-id="627a2-122">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="627a2-122">This example requires:</span></span>  
  
- <span data-ttu-id="627a2-123">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="627a2-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627a2-124">참조</span><span class="sxs-lookup"><span data-stu-id="627a2-124">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="627a2-125">지역화</span><span class="sxs-lookup"><span data-stu-id="627a2-125">Localization</span></span>](../../../standard/globalization-localization/localization.md)
