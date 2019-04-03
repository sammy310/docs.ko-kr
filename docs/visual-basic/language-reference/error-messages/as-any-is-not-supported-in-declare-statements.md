---
title: "'Declare' 문에서는 'As Any'가 지원되지 않습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: c6c792e02bb655dc8a9544c4b5b46a64210556f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839927"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="da5ea-102">'Declare' 문에서는 'As Any'가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5ea-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="da5ea-103">합니다 `Any` 데이터 형식을 사용한 `Declare` Visual Basic 6.0 및 이전 버전의 모든 종류의 데이터를 포함할 수 있는 인수 사용을 허용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="da5ea-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="da5ea-104">하지만 오버 로드를 허용, Visual Basic 지원 하 고 따라서로 전환 합니다 `Any` 데이터 형식은 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5ea-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="da5ea-105">**오류 ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="da5ea-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da5ea-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="da5ea-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="da5ea-107">사용 하려는 특정 형식의 매개 변수를 선언 합니다. 예를 들어.</span><span class="sxs-lookup"><span data-stu-id="da5ea-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  <span data-ttu-id="da5ea-108">사용 된 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 지정 하는 특성 `As Any` 때 `Void*` 호출 되는 프로시저에서 예상 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5ea-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="da5ea-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="da5ea-109">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="da5ea-110">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="da5ea-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="da5ea-111">Declare 문</span><span class="sxs-lookup"><span data-stu-id="da5ea-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="da5ea-112">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="da5ea-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
