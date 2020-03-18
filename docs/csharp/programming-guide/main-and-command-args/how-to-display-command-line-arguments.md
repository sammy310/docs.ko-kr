---
title: 명령줄 인수를 표시하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 210dad71220572535a0325fac925b0453b0d4e03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712028"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="d3139-102">명령줄 인수를 표시하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d3139-102">How to display command line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="d3139-103">명령줄에서 실행 파일에 제공된 인수는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="d3139-104">인수는 문자열 배열의 형태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="d3139-105">배열의 각 요소에는 하나의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="d3139-106">인수 사이의 공백은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-106">White-space between arguments is removed.</span></span> <span data-ttu-id="d3139-107">예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="d3139-108">명령줄 입력</span><span class="sxs-lookup"><span data-stu-id="d3139-108">Input on Command-line</span></span>|<span data-ttu-id="d3139-109">Main에 전달되는 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="d3139-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="d3139-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="d3139-110">**executable.exe a b c**</span></span>|<span data-ttu-id="d3139-111">"a"</span><span class="sxs-lookup"><span data-stu-id="d3139-111">"a"</span></span><br /><br /> <span data-ttu-id="d3139-112">"b"</span><span class="sxs-lookup"><span data-stu-id="d3139-112">"b"</span></span><br /><br /> <span data-ttu-id="d3139-113">"c"</span><span class="sxs-lookup"><span data-stu-id="d3139-113">"c"</span></span>|  
|<span data-ttu-id="d3139-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="d3139-114">**executable.exe one two**</span></span>|<span data-ttu-id="d3139-115">"one"</span><span class="sxs-lookup"><span data-stu-id="d3139-115">"one"</span></span><br /><br /> <span data-ttu-id="d3139-116">"two"</span><span class="sxs-lookup"><span data-stu-id="d3139-116">"two"</span></span>|  
|<span data-ttu-id="d3139-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="d3139-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="d3139-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="d3139-118">"one two"</span></span><br /><br /> <span data-ttu-id="d3139-119">"three"</span><span class="sxs-lookup"><span data-stu-id="d3139-119">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d3139-120">Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3139-121">예제</span><span class="sxs-lookup"><span data-stu-id="d3139-121">Example</span></span>  
 <span data-ttu-id="d3139-122">이 예제에서는 명령줄 애플리케이션에 전달된 명령줄 인수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="d3139-123">위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3139-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d3139-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3139-124">See also</span></span>

- [<span data-ttu-id="d3139-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d3139-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d3139-126">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="d3139-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="d3139-127">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="d3139-127">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="d3139-128">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="d3139-128">Main() Return Values</span></span>](./main-return-values.md)
