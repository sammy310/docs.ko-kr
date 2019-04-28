---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4f3dc61a6e78b0fb2135d4132c53e7efc22447a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789053"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="61ace-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61ace-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="61ace-103">컴파일러가를 자동으로 표준 라이브러리를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ace-104">구문</span><span class="sxs-lookup"><span data-stu-id="61ace-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="61ace-105">설명</span><span class="sxs-lookup"><span data-stu-id="61ace-105">Remarks</span></span>  
 <span data-ttu-id="61ace-106">`-nostdlib` 옵션 System.dll 어셈블리에 대 한 자동 참조를 제거 하 고 컴파일러에서 Vbc.rsp 파일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="61ace-107">Vbc.exe 파일과 동일한 디렉터리에 위치한 Vbc.rsp 파일을 자주 사용 되는 참조 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리 및 가져오기는 `System` 고 `Microsoft.VisualBasic` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61ace-108">Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61ace-109">`-nostdlib` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61ace-110">예제</span><span class="sxs-lookup"><span data-stu-id="61ace-110">Example</span></span>  
 <span data-ttu-id="61ace-111">다음 코드에서는 `T2.vb` 표준 라이브러리를 참조 하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ace-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="61ace-112">설정 해야 합니다 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"를 제거 하는 `My` 개체.</span><span class="sxs-lookup"><span data-stu-id="61ace-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="61ace-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="61ace-113">See also</span></span>

- [<span data-ttu-id="61ace-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="61ace-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="61ace-115">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="61ace-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="61ace-116">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="61ace-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="61ace-117">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="61ace-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
