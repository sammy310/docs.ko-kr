---
title: '방법: BindingSource가 있는 Windows Forms 컨트롤에서 데이터 원본 업데이트 반영'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: e3ee6fd0f90840a8af3322e5ed66c0f7885211ae
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614695"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="a31a3-102">방법: BindingSource가 있는 Windows Forms 컨트롤에서 데이터 원본 업데이트 반영</span><span class="sxs-lookup"><span data-stu-id="a31a3-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="a31a3-103">데이터 바인딩된 컨트롤을 사용하는 경우 데이터 소스에서 목록 변경 이벤트가 발생하지 않을 때 데이터 소스의 변경 내용에 대응해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="a31a3-104"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 데이터 소스를 Windows Forms 컨트롤에 바인딩하는 경우 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 메서드를 호출하여 데이터 소스가 변경된 것을 컨트롤에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a31a3-105">예제</span><span class="sxs-lookup"><span data-stu-id="a31a3-105">Example</span></span>  
 <span data-ttu-id="a31a3-106">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 메서드를 사용하여 바인딩된 컨트롤에 데이터 소스 업데이트에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a31a3-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a31a3-107">Compiling the Code</span></span>  
 <span data-ttu-id="a31a3-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-108">This example requires:</span></span>  
  
- <span data-ttu-id="a31a3-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a31a3-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a31a3-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a31a3-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a31a3-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31a3-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a31a3-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="a31a3-113">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a31a3-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="a31a3-114">방법: 형식에는 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="a31a3-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
