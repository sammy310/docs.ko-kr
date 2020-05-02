---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347908"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="e41c6-102">-nostdlib(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e41c6-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="e41c6-103">컴파일러가 표준 라이브러리를 자동으로 참조하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e41c6-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="e41c6-105">설명</span><span class="sxs-lookup"><span data-stu-id="e41c6-105">Remarks</span></span>  
 <span data-ttu-id="e41c6-106">`-nostdlib` 옵션은 System.dll 어셈블리에 대한 자동 참조를 제거하고 컴파일러에서 Vbc.rsp 파일을 읽을 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="e41c6-107">Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일은 일반적으로 사용되는 .NET Framework 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e41c6-108">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e41c6-109">Visual Studio 개발 환경 내에서는 `-nostdlib` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e41c6-110">예제</span><span class="sxs-lookup"><span data-stu-id="e41c6-110">Example</span></span>  
 <span data-ttu-id="e41c6-111">다음 코드는 표준 라이브러리를 참조하지 않고 `T2.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="e41c6-112">`My` 개체를 제거하려면 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41c6-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e41c6-113">참조</span><span class="sxs-lookup"><span data-stu-id="e41c6-113">See also</span></span>

- [<span data-ttu-id="e41c6-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="e41c6-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="e41c6-115">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="e41c6-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e41c6-116">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="e41c6-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="e41c6-117">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e41c6-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
