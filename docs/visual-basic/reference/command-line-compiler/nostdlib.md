---
description: '자세한 정보: -nostdlib(Visual Basic)'
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4a00ad21bc0038a6bf42f1dd6943ccc15c1a8abb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434877"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="ca66d-103">-nostdlib(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca66d-103">-nostdlib (Visual Basic)</span></span>

<span data-ttu-id="ca66d-104">컴파일러가 표준 라이브러리를 자동으로 참조하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-104">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca66d-105">구문</span><span class="sxs-lookup"><span data-stu-id="ca66d-105">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="ca66d-106">설명</span><span class="sxs-lookup"><span data-stu-id="ca66d-106">Remarks</span></span>  

 <span data-ttu-id="ca66d-107">`-nostdlib` 옵션은 System.dll 어셈블리에 대한 자동 참조를 제거하고 컴파일러에서 Vbc.rsp 파일을 읽을 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-107">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="ca66d-108">Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일은 일반적으로 사용되는 .NET Framework 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-108">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca66d-109">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-109">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca66d-110">Visual Studio 개발 환경 내에서는 `-nostdlib` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-110">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca66d-111">예제</span><span class="sxs-lookup"><span data-stu-id="ca66d-111">Example</span></span>  

 <span data-ttu-id="ca66d-112">다음 코드는 표준 라이브러리를 참조하지 않고 `T2.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-112">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="ca66d-113">`My` 개체를 제거하려면 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca66d-113">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca66d-114">참조</span><span class="sxs-lookup"><span data-stu-id="ca66d-114">See also</span></span>

- [<span data-ttu-id="ca66d-115">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ca66d-115">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="ca66d-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ca66d-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ca66d-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="ca66d-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="ca66d-118">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ca66d-118">Customizing Which Objects are Available in My</span></span>](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
