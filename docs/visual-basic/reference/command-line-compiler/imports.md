---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: cc9fc222843bdfe8e49d2d291dc36ff3e0c63fc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408597"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="fb7b7-102">-imports(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb7b7-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="fb7b7-103">지정된 어셈블리에서 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="fb7b7-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb7b7-105">인수</span><span class="sxs-lookup"><span data-stu-id="fb7b7-105">Arguments</span></span>  
  
|<span data-ttu-id="fb7b7-106">용어</span><span class="sxs-lookup"><span data-stu-id="fb7b7-106">Term</span></span>|<span data-ttu-id="fb7b7-107">정의</span><span class="sxs-lookup"><span data-stu-id="fb7b7-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="fb7b7-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-108">Required.</span></span> <span data-ttu-id="fb7b7-109">가져올 쉼표로 구분된 네임스페이스 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb7b7-110">설명</span><span class="sxs-lookup"><span data-stu-id="fb7b7-110">Remarks</span></span>  
 <span data-ttu-id="fb7b7-111">`-imports` 옵션은 현재 원본 파일 세트 또는 참조된 어셈블리에서 정의된 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="fb7b7-112">`-imports`로 지정된 네임스페이스의 멤버는 컴파일 시 모든 소스 코드 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="fb7b7-113">[Imports 문(.NET 네임스페이스 및 형식)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)을 사용하여 단일 소스 코드 파일에서 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-113">Use the [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="fb7b7-114">Visual Studio 통합 개발 환경에서 -imports를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="fb7b7-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fb7b7-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="fb7b7-117">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="fb7b7-118">3.  **사용자 가져오기 추가** 단추 옆의 상자에 네임스페이스 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="fb7b7-119">4.  **사용자 가져오기 추가** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fb7b7-120">예제</span><span class="sxs-lookup"><span data-stu-id="fb7b7-120">Example</span></span>  
 <span data-ttu-id="fb7b7-121">다음 코드는 `-imports:system.globalization`이 지정될 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="fb7b7-122">이를 사용하지 않고 성공적으로 컴파일하려면 소스 코드 파일의 시작 부분에 `Imports System.Globalization` 문이 포함되거나 속성이 `System.Globalization.CultureInfo.CurrentCulture.Name`으로 정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="fb7b7-123">참조</span><span class="sxs-lookup"><span data-stu-id="fb7b7-123">See also</span></span>

- [<span data-ttu-id="fb7b7-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fb7b7-124">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fb7b7-125">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="fb7b7-125">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="fb7b7-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fb7b7-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
