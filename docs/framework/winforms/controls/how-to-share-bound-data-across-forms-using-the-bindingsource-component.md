---
title: '방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 19505c690728147d2a67c26371e1cea4c281ab08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154872"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="f5a13-102">방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="f5a13-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="f5a13-103"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 폼 간에 데이터를 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="f5a13-104">예를 들어 데이터 소스 데이터를 요약하는 하나의 읽기 전용 폼과 데이터 소스에서 현재 선택한 항목에 대한 세부 정보가 포함된 다른 편집 가능한 폼을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="f5a13-105">이 예제에서는 이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a13-106">예제</span><span class="sxs-lookup"><span data-stu-id="f5a13-106">Example</span></span>  
 <span data-ttu-id="f5a13-107">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 및 바인딩된 데이터를 폼 간에 공유하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="f5a13-108">이 예제에서는 공유 <xref:System.Windows.Forms.BindingSource>는 자식 폼의 생성자에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="f5a13-109">자식 폼을 통해 사용자는 기본 폼에서 현재 선택한 항목에 대한 데이터를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5a13-110">예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리하여 두 폼을 동기화된 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="f5a13-111">내용은 이유에 대 한 자세한 내용은 이루어집니다 [방법: 여러 컨트롤을 확인 동일한 데이터 소스에 바인딩된 동기화 된 상태로 유지](../multiple-controls-bound-to-data-source-synchronized.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5a13-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f5a13-112">Compiling the Code</span></span>  
 <span data-ttu-id="f5a13-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-113">This example requires:</span></span>  
  
-   <span data-ttu-id="f5a13-114">System, System.Windows.Forms, System.Drawing, System.Data 및 System.Xml 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f5a13-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="f5a13-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f5a13-116">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a13-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a13-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5a13-117">See also</span></span>

- [<span data-ttu-id="f5a13-118">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f5a13-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="f5a13-119">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="f5a13-119">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="f5a13-120">방법: 오류 및 데이터 바인딩에서 발생 하는 예외 처리</span><span class="sxs-lookup"><span data-stu-id="f5a13-120">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
