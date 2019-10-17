---
title: '방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396017"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="91304-102">방법: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="91304-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="91304-103">좋은 레이아웃은 부모 폼의 크기 변경에 제대로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="91304-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="91304-104"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 폼의 레이아웃을 정렬하면 폼 크기가 변경될 때 일관된 방식으로 컨트롤의 크기를 조정하고 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91304-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="91304-105"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 컨트롤의 콘텐츠 변경으로 인해 레이아웃이 변경되는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="91304-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="91304-106">이 절차에서 설명하는 프로세스는 Visual Studio 환경 내에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91304-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="91304-107">또한 [연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91304-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91304-108">예제</span><span class="sxs-lookup"><span data-stu-id="91304-108">Example</span></span>  
 <span data-ttu-id="91304-109">다음 예제에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 사용자가 폼 크기를 조정할 때 제대로 대응하는 레이아웃을 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91304-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="91304-110">또한 지역화에 제대로 대응하는 레이아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91304-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91304-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="91304-111">Compiling the Code</span></span>  
 <span data-ttu-id="91304-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="91304-112">This example requires:</span></span>  
  
- <span data-ttu-id="91304-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="91304-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91304-114">참조</span><span class="sxs-lookup"><span data-stu-id="91304-114">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="91304-115">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="91304-115">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="91304-116">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="91304-116">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
