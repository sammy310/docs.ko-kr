---
description: '#ExternalSource 지시문에 대해 자세히 알아보세요.'
title: '#ExternalSource 지시문'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 1f2e73aa152fbe2d97edcde912626696faacd5af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797239"
---
# <a name="externalsource-directive"></a><span data-ttu-id="b8a73-103">#ExternalSource 지시문</span><span class="sxs-lookup"><span data-stu-id="b8a73-103">#ExternalSource Directive</span></span>

<span data-ttu-id="b8a73-104">소스 코드의 특정 줄과 소스 외부의 텍스트 간 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-104">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a73-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8a73-105">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="b8a73-106">부분</span><span class="sxs-lookup"><span data-stu-id="b8a73-106">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="b8a73-107">외부 소스에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-107">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="b8a73-108">외부 소스 첫째 줄의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-108">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="b8a73-109">외부 소스에서 오류가 발생 하는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-109">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="b8a73-110">`#ExternalSource` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-110">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a73-111">설명</span><span class="sxs-lookup"><span data-stu-id="b8a73-111">Remarks</span></span>  

 <span data-ttu-id="b8a73-112">이 지시문은 컴파일러와 디버거에서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-112">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="b8a73-113">소스 파일에는 소스 파일의 특정 코드 줄과 소스 외부의 텍스트 (예: .aspx 파일) 간의 매핑을 나타내는 외부 소스 지시문이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-113">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="b8a73-114">컴파일 중에 지정 된 소스 코드에서 오류가 발생 하면 외부 소스에서 가져온 것으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-114">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="b8a73-115">외부 소스 지시문은 컴파일에 영향을 주지 않으며 중첩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-115">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="b8a73-116">응용 프로그램에서 내부용으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8a73-116">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a73-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8a73-117">See also</span></span>

- [<span data-ttu-id="b8a73-118">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="b8a73-118">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
