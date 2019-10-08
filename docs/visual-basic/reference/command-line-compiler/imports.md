---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 929e24a1ffd02d4e21ab1b925ddd59050b5d3cc4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005568"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="498eb-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="498eb-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="498eb-103">지정 된 어셈블리에서 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="498eb-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="498eb-105">인수</span><span class="sxs-lookup"><span data-stu-id="498eb-105">Arguments</span></span>  
  
|<span data-ttu-id="498eb-106">용어</span><span class="sxs-lookup"><span data-stu-id="498eb-106">Term</span></span>|<span data-ttu-id="498eb-107">정의</span><span class="sxs-lookup"><span data-stu-id="498eb-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="498eb-108">필수.</span><span class="sxs-lookup"><span data-stu-id="498eb-108">Required.</span></span> <span data-ttu-id="498eb-109">가져올 쉼표로 구분 된 네임 스페이스 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="498eb-110">설명</span><span class="sxs-lookup"><span data-stu-id="498eb-110">Remarks</span></span>  
 <span data-ttu-id="498eb-111">@No__t-0 옵션은 소스 파일의 현재 집합 또는 참조 된 어셈블리에서 정의 된 모든 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="498eb-112">@No__t-0으로 지정 된 네임 스페이스의 멤버는 컴파일할 때 모든 소스 코드 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="498eb-113">[Imports 문 (.Net 네임 스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 을 사용 하 여 단일 소스 코드 파일에서 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="498eb-114">Visual Studio 통합 개발 환경에서/imports를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="498eb-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="498eb-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="498eb-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="498eb-117">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="498eb-118">3.  **사용자 가져오기 추가** 단추 옆의 상자에 네임 스페이스 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="498eb-119">4.  **사용자 가져오기 추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="498eb-120">예제</span><span class="sxs-lookup"><span data-stu-id="498eb-120">Example</span></span>  
 <span data-ttu-id="498eb-121">다음 코드는 `/imports:system.globalization`이 지정 될 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="498eb-122">이 기능을 사용 하지 않으면 `Imports System.Globalization` 문이 소스 코드 파일의 시작 부분에 포함 되거나 속성이 `System.Globalization.CultureInfo.CurrentCulture.Name`로 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="498eb-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="498eb-123">참조</span><span class="sxs-lookup"><span data-stu-id="498eb-123">See also</span></span>

- [<span data-ttu-id="498eb-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="498eb-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="498eb-125">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="498eb-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="498eb-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="498eb-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
