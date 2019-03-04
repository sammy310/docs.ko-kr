---
title: '방법: foreach를 사용하여 명령줄 인수 액세스 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 5813ad573e89886ba991ca8cbcebb7232af05821
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971678"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="112ba-102">방법: foreach를 사용하여 명령줄 인수 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="112ba-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="112ba-103">배열을 반복하는 또 다른 방법은 이 예제에 표시된 대로 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="112ba-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="112ba-104">`foreach` 문은 배열, .NET Framework 컬렉션 클래스 또는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 임의의 클래스나 구조체를 반복하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ba-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="112ba-105">Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="112ba-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="112ba-106">예제</span><span class="sxs-lookup"><span data-stu-id="112ba-106">Example</span></span>  
 <span data-ttu-id="112ba-107">이 예제에서는 `foreach`를 사용하여 명령줄을 출력하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="112ba-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class2.cs#10)]  
  
 [!code-csharp[csProgGuideMain#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="112ba-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="112ba-108">See also</span></span>

- <xref:System.Array>
- <xref:System.Collections>
- [<span data-ttu-id="112ba-109">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="112ba-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="112ba-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="112ba-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="112ba-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="112ba-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="112ba-112">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="112ba-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="112ba-113">방법: 명령줄 인수 표시</span><span class="sxs-lookup"><span data-stu-id="112ba-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="112ba-114">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="112ba-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
