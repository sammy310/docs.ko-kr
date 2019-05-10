---
title: '방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: cffcdbbaa988033352b08834e52d603fbebfa870
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591603"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="d44f3-102">방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="d44f3-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="d44f3-103">이 예제에서는 Windows Forms 컨트롤에서 발생할 수 있는 대부분의 키보드, 마우스, 포커스 및 유효성 검사 이벤트를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="d44f3-104">포커스가 있을 경우 `TextBoxInput`이라는 텍스트 상자가 이벤트를 수신하며, 각 이벤트에 대한 정보가 이벤트 발생 순서대로 `TextBoxOutput`이라는 텍스트 상자에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="d44f3-105">애플리케이션에는 보고할 이벤트를 필터링하는 데 사용할 수 있는 확인란 집합도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d44f3-106">예제</span><span class="sxs-lookup"><span data-stu-id="d44f3-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d44f3-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d44f3-107">Compiling the Code</span></span>  
 <span data-ttu-id="d44f3-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-108">This example requires:</span></span>  
  
- <span data-ttu-id="d44f3-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d44f3-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d44f3-110">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d44f3-111">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d44f3-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44f3-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d44f3-112">See also</span></span>

- [<span data-ttu-id="d44f3-113">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="d44f3-113">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
