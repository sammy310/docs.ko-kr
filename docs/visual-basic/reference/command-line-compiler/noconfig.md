---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588851"
---
# <a name="-noconfig"></a><span data-ttu-id="c5fe6-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="c5fe6-102">-noconfig</span></span>
<span data-ttu-id="c5fe6-103">컴파일러를 자동으로 자주 사용 되는.NET Framework 어셈블리 참조, 가져오기 지정 합니다 `System` 고 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5fe6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5fe6-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5fe6-105">설명</span><span class="sxs-lookup"><span data-stu-id="c5fe6-105">Remarks</span></span>  
 <span data-ttu-id="c5fe6-106">`-noconfig` 옵션 하 Vbc.exe 파일과 동일한 디렉터리에 위치한 Vbc.rsp 파일을 컴파일하지 않도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="c5fe6-107">Vbc.rsp 파일을 자주 사용 되는.NET Framework 어셈블리를 참조 하 고 가져옵니다 합니다 `System` 고 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="c5fe6-108">컴파일러는 암시적으로 System.dll 어셈블리를 참조 하지 않는 한는 `-nostdlib` 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="c5fe6-109">`-nostdlib` 옵션은 Vbc.rsp로 컴파일하지 또는 System.dll 어셈블리를 자동으로 참조 하지 않도록 컴파일러 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5fe6-110">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="c5fe6-111">Vbc.exe 컴파일할 때마다 포함 되어야 하는 추가 컴파일러 옵션을 지정 하려면 Vbc.rsp 파일을 수정할 수 있습니다 (지정 하는 경우를 제외 하 고는 `-noconfig` 옵션).</span><span class="sxs-lookup"><span data-stu-id="c5fe6-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="c5fe6-112">자세한 내용은 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="c5fe6-113">컴파일러에 전달 된 옵션을 처리 합니다 `vbc` 마지막 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="c5fe6-114">따라서 명령줄의 모든 옵션은 Vbc.rsp 파일에 동일한 옵션의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5fe6-115">`-noconfig` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5fe6-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5fe6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5fe6-116">See also</span></span>

- [<span data-ttu-id="c5fe6-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5fe6-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="c5fe6-118">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c5fe6-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c5fe6-119">@(지시 파일 지정)</span><span class="sxs-lookup"><span data-stu-id="c5fe6-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="c5fe6-120">-참조 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5fe6-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
