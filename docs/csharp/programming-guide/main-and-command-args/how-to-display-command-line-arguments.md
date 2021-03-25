---
title: 명령줄 인수를 표시하는 방법 - C# 프로그래밍 가이드
description: 명령줄 인수를 표시하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 03/08/2021
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 7c3e8d7f6ad2a599308057e996808509e70b7508
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480268"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="04121-104">명령줄 인수를 표시하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="04121-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="04121-105">명령줄에서 실행 파일에 제공된 인수는 [최상위 문](top-level-statements.md) 또는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04121-105">Arguments provided to an executable on the command line are accessible in [top-level statements](top-level-statements.md) or through an optional parameter to `Main`.</span></span> <span data-ttu-id="04121-106">인수는 문자열 배열의 형태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="04121-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="04121-107">배열의 각 요소에는 하나의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04121-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="04121-108">인수 사이의 공백은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="04121-108">White-space between arguments is removed.</span></span> <span data-ttu-id="04121-109">예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="04121-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="04121-110">명령줄 입력</span><span class="sxs-lookup"><span data-stu-id="04121-110">Input on command line</span></span>|<span data-ttu-id="04121-111">Main에 전달되는 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="04121-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="04121-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="04121-112">**executable.exe a b c**</span></span>|<span data-ttu-id="04121-113">"a"</span><span class="sxs-lookup"><span data-stu-id="04121-113">"a"</span></span><br /><br /> <span data-ttu-id="04121-114">"b"</span><span class="sxs-lookup"><span data-stu-id="04121-114">"b"</span></span><br /><br /> <span data-ttu-id="04121-115">"c"</span><span class="sxs-lookup"><span data-stu-id="04121-115">"c"</span></span>|  
|<span data-ttu-id="04121-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="04121-116">**executable.exe one two**</span></span>|<span data-ttu-id="04121-117">"one"</span><span class="sxs-lookup"><span data-stu-id="04121-117">"one"</span></span><br /><br /> <span data-ttu-id="04121-118">"two"</span><span class="sxs-lookup"><span data-stu-id="04121-118">"two"</span></span>|  
|<span data-ttu-id="04121-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="04121-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="04121-120">"one two"</span><span class="sxs-lookup"><span data-stu-id="04121-120">"one two"</span></span><br /><br /> <span data-ttu-id="04121-121">"three"</span><span class="sxs-lookup"><span data-stu-id="04121-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="04121-122">Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04121-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04121-123">예제</span><span class="sxs-lookup"><span data-stu-id="04121-123">Example</span></span>  

 <span data-ttu-id="04121-124">이 예제에서는 명령줄 애플리케이션에 전달된 명령줄 인수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04121-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="04121-125">위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04121-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="04121-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04121-126">See also</span></span>

- [<span data-ttu-id="04121-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04121-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04121-128">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="04121-128">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="04121-129">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="04121-129">Main() Return Values</span></span>](./main-return-values.md)
