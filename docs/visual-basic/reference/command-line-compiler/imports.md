---
title: -가져오기 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 075eeccc7d80943d2757a97b9a355bbea3ef9d4e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833612"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="73382-102">-가져오기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73382-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="73382-103">지정된 된 어셈블리에서 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73382-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73382-104">구문</span><span class="sxs-lookup"><span data-stu-id="73382-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="73382-105">인수</span><span class="sxs-lookup"><span data-stu-id="73382-105">Arguments</span></span>  
  
|<span data-ttu-id="73382-106">용어</span><span class="sxs-lookup"><span data-stu-id="73382-106">Term</span></span>|<span data-ttu-id="73382-107">정의</span><span class="sxs-lookup"><span data-stu-id="73382-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="73382-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="73382-108">Required.</span></span> <span data-ttu-id="73382-109">가져올 네임 스페이스의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="73382-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73382-110">설명</span><span class="sxs-lookup"><span data-stu-id="73382-110">Remarks</span></span>  
 <span data-ttu-id="73382-111">`-imports` 옵션 현재 소스 파일 또는 모든 참조 된 어셈블리에서 집합 내에 정의 된 모든 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73382-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="73382-112">지정 된 네임 스페이스의 멤버 `-imports` 컴파일할 때 모든 소스 코드 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73382-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="73382-113">사용 된 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 단일 소스 코드 파일에서 네임 스페이스를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="73382-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="73382-114">설정 하려면 Visual Studio 통합된 개발 환경에서 가져오기 /</span><span class="sxs-lookup"><span data-stu-id="73382-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="73382-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73382-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73382-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73382-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="73382-117">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="73382-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="73382-118">3.  옆의 상자에 네임 스페이스 이름을 입력 합니다 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="73382-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="73382-119">4.  클릭 합니다 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="73382-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73382-120">예제</span><span class="sxs-lookup"><span data-stu-id="73382-120">Example</span></span>  
 <span data-ttu-id="73382-121">다음 코드는 경우 `/imports:system.globalization` 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73382-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="73382-122">없으면 성공적으로 컴파일 중에 나 필요는 `Imports System.Globalization` 소스 코드 파일의 시작 부분에 문을 포함할 또는 속성으로 정규화 되어야 `System.Globalization.CultureInfo.CurrentCulture.Name`합니다.</span><span class="sxs-lookup"><span data-stu-id="73382-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="73382-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="73382-123">See also</span></span>

- [<span data-ttu-id="73382-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="73382-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="73382-125">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="73382-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="73382-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="73382-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
