---
description: '자세한 정보: -noconfig'
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: e97d44427b537e73a404a47d30db202e2c3b1f41
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481690"
---
# <a name="-noconfig"></a><span data-ttu-id="89bef-103">-noconfig</span><span class="sxs-lookup"><span data-stu-id="89bef-103">-noconfig</span></span>

<span data-ttu-id="89bef-104">컴파일러가 일반적으로 사용되는 .NET Framework 어셈블리를 자동으로 참조하지 않도록 하거나 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져오지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-104">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89bef-105">구문</span><span class="sxs-lookup"><span data-stu-id="89bef-105">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="89bef-106">설명</span><span class="sxs-lookup"><span data-stu-id="89bef-106">Remarks</span></span>  

 <span data-ttu-id="89bef-107">`-noconfig` 옵션은 Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일로 컴파일하지 않도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-107">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="89bef-108">Vbc.rsp 파일은 일반적으로 사용되는 .NET Framework 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-108">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="89bef-109">컴파일러는 `-nostdlib` 옵션이 지정되지 않는 한 System.dll 어셈블리를 암시적으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-109">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="89bef-110">`-nostdlib` 옵션은 Vbc.rsp를 사용하여 컴파일하지 않도록 하거나 System.dll 어셈블리를 자동으로 참조하지 않도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-110">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89bef-111">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-111">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="89bef-112">Vbc.rsp 파일을 수정하여 모든 Vbc.exe 컴파일에 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다(`-noconfig` 옵션을 지정할 경우 제외).</span><span class="sxs-lookup"><span data-stu-id="89bef-112">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="89bef-113">자세한 내용은 [@ (지시 파일 지정)](specify-response-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89bef-113">For more information, see [@ (Specify Response File)](specify-response-file.md).</span></span>  
  
 <span data-ttu-id="89bef-114">컴파일러는 `vbc` 명령에 마지막으로 전달된 옵션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-114">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="89bef-115">따라서 명령줄의 모든 옵션은 Vbc.rsp 파일에 있는 동일한 옵션의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-115">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89bef-116">Visual Studio 개발 환경 내에서는 `-noconfig` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89bef-116">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bef-117">참조</span><span class="sxs-lookup"><span data-stu-id="89bef-117">See also</span></span>

- [<span data-ttu-id="89bef-118">-nostdlib(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89bef-118">-nostdlib (Visual Basic)</span></span>](nostdlib.md)
- [<span data-ttu-id="89bef-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="89bef-119">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="89bef-120">@(지시 파일 지정)</span><span class="sxs-lookup"><span data-stu-id="89bef-120">@ (Specify Response File)</span></span>](specify-response-file.md)
- [<span data-ttu-id="89bef-121">-reference(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89bef-121">-reference (Visual Basic)</span></span>](reference.md)
