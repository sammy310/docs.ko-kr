---
title: '#ExternalSource 지시문 (Visual Basic)'
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
ms.openlocfilehash: ac7096e998dd8d2a416dc739e1d7625e1abff7a6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696832"
---
# <a name="externalsource-directive"></a><span data-ttu-id="625c0-102">#ExternalSource 지시문</span><span class="sxs-lookup"><span data-stu-id="625c0-102">#ExternalSource Directive</span></span>
<span data-ttu-id="625c0-103">소스 코드의 특정 줄과 소스 외부의 텍스트 간 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="625c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="625c0-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="625c0-105">요소</span><span class="sxs-lookup"><span data-stu-id="625c0-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="625c0-106">외부 소스에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="625c0-107">외부 소스 첫째 줄의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="625c0-108">외부 소스에서 오류가 발생 하는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="625c0-109">`#ExternalSource` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="625c0-110">설명</span><span class="sxs-lookup"><span data-stu-id="625c0-110">Remarks</span></span>  
 <span data-ttu-id="625c0-111">이 지시문은 컴파일러와 디버거에서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="625c0-112">소스 파일에는 소스 파일의 특정 코드 줄과 소스 외부의 텍스트 (예: .aspx 파일) 간의 매핑을 나타내는 외부 소스 지시문이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="625c0-113">컴파일 중에 지정 된 소스 코드에서 오류가 발생 하면 외부 소스에서 가져온 것으로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="625c0-114">외부 소스 지시문은 컴파일에 영향을 주지 않으며 중첩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="625c0-115">응용 프로그램에서 내부용으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625c0-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625c0-116">참조</span><span class="sxs-lookup"><span data-stu-id="625c0-116">See also</span></span>

- [<span data-ttu-id="625c0-117">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="625c0-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
