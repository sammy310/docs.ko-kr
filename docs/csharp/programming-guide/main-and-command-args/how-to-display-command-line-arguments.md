---
title: '방법: 명령줄 인수 표시 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: b7018afa1272f4ae092863de6b7f9ef783001244
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965594"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="9e43f-102">방법: 명령줄 인수 표시(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9e43f-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="9e43f-103">명령줄에서 실행 파일에 제공된 인수는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="9e43f-104">인수는 문자열 배열의 형태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="9e43f-105">배열의 각 요소에는 하나의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="9e43f-106">인수 사이의 공백은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-106">White-space between arguments is removed.</span></span> <span data-ttu-id="9e43f-107">예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="9e43f-108">명령줄 입력</span><span class="sxs-lookup"><span data-stu-id="9e43f-108">Input on Command-line</span></span>|<span data-ttu-id="9e43f-109">Main에 전달되는 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="9e43f-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="9e43f-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="9e43f-110">**executable.exe a b c**</span></span>|<span data-ttu-id="9e43f-111">"a"</span><span class="sxs-lookup"><span data-stu-id="9e43f-111">"a"</span></span><br /><br /> <span data-ttu-id="9e43f-112">"b"</span><span class="sxs-lookup"><span data-stu-id="9e43f-112">"b"</span></span><br /><br /> <span data-ttu-id="9e43f-113">"c"</span><span class="sxs-lookup"><span data-stu-id="9e43f-113">"c"</span></span>|  
|<span data-ttu-id="9e43f-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="9e43f-114">**executable.exe one two**</span></span>|<span data-ttu-id="9e43f-115">"one"</span><span class="sxs-lookup"><span data-stu-id="9e43f-115">"one"</span></span><br /><br /> <span data-ttu-id="9e43f-116">"two"</span><span class="sxs-lookup"><span data-stu-id="9e43f-116">"two"</span></span>|  
|<span data-ttu-id="9e43f-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="9e43f-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="9e43f-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="9e43f-118">"one two"</span></span><br /><br /> <span data-ttu-id="9e43f-119">"three"</span><span class="sxs-lookup"><span data-stu-id="9e43f-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9e43f-120">Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e43f-121">예제</span><span class="sxs-lookup"><span data-stu-id="9e43f-121">Example</span></span>  
 <span data-ttu-id="9e43f-122">이 예제에서는 명령줄 애플리케이션에 전달된 명령줄 인수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="9e43f-123">위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e43f-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="9e43f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e43f-124">See also</span></span>

- [<span data-ttu-id="9e43f-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9e43f-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9e43f-126">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="9e43f-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="9e43f-127">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="9e43f-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="9e43f-128">방법: foreach를 사용하여 명령줄 인수 액세스</span><span class="sxs-lookup"><span data-stu-id="9e43f-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [<span data-ttu-id="9e43f-129">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="9e43f-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
