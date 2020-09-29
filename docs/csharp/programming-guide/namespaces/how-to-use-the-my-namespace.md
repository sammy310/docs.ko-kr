---
title: My 네임스페이스를 사용하는 방법 - C# 프로그래밍 가이드
description: "'My' 네임스페이스에 대해 알아봅니다. 'My' 네임스페이스는 다양한 .NET 클래스에 대한 쉽고 직관적인 액세스를 제공합니다."
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 5310b911cc0abf0e82c4dc8efd45eb45ffb94c9d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176229"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="fd3b7-104">My 네임스페이스를 사용하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fd3b7-104">How to use the My namespace (C# Programming Guide)</span></span>

<span data-ttu-id="fd3b7-105"><xref:Microsoft.VisualBasic.MyServices> 네임스페이스(Visual Basic의 `My`)는 여러 .NET 클래스에 대한 쉽고 직관적인 액세스를 제공하여 컴퓨터, 애플리케이션, 설정, 리소스 등을 조작하는 코드를 작성할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-105">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="fd3b7-106">원래 Visual Basic에서 사용하도록 설계되었지만 `MyServices` 네임스페이스는 C# 애플리케이션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-106">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="fd3b7-107">Visual Basic에서 `MyServices` 네임스페이스를 사용하는 방법에 대한 자세한 내용은 [My를 사용한 개발](../../../visual-basic/developing-apps/development-with-my/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-107">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="add-a-reference"></a><span data-ttu-id="fd3b7-108">참조 추가</span><span class="sxs-lookup"><span data-stu-id="fd3b7-108">Add a reference</span></span>

 <span data-ttu-id="fd3b7-109">솔루션에서 `MyServices` 클래스를 사용하려면 먼저 Visual Basic 라이브러리에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-109">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
### <a name="add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="fd3b7-110">Visual Basic 라이브러리에 대한 참조 추가</span><span class="sxs-lookup"><span data-stu-id="fd3b7-110">Add a reference to the Visual Basic library</span></span>  
  
1. <span data-ttu-id="fd3b7-111">**솔루션 탐색기**에서 **참조** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-111">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="fd3b7-112">**참조** 대화 상자가 나타나면 목록 아래로 스크롤한 다음 Microsoft.VisualBasic.dll을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-112">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="fd3b7-113">프로그램의 시작 부분에 있는 `using` 섹션에 다음 줄을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-113">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a><span data-ttu-id="fd3b7-114">예제</span><span class="sxs-lookup"><span data-stu-id="fd3b7-114">Example</span></span>  

 <span data-ttu-id="fd3b7-115">이 예제에서는 `MyServices` 네임스페이스에 포함된 다양한 정적 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-115">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="fd3b7-116">이 코드를 컴파일하려면 Microsoft.VisualBasic.DLL에 대한 참조를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-116">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 <span data-ttu-id="fd3b7-117">`MyServices` 네임스페이스의 모든 클래스를 C# 애플리케이션에서 호출할 수 있는 것은 아닙니다. 예를 들어 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> 클래스는 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="fd3b7-118">이 특정한 경우에는 <xref:Microsoft.VisualBasic.FileIO.FileSystem>의 일부이고 VisualBasic.dll에도 포함된 정적 메서드를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="fd3b7-119">예를 들어 이러한 메서드 중 하나를 사용하여 디렉터리를 복제하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3b7-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a><span data-ttu-id="fd3b7-120">참조</span><span class="sxs-lookup"><span data-stu-id="fd3b7-120">See also</span></span>

- [<span data-ttu-id="fd3b7-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fd3b7-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fd3b7-122">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fd3b7-122">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="fd3b7-123">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="fd3b7-123">Using Namespaces</span></span>](./using-namespaces.md)
