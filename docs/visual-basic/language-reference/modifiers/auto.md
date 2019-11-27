---
title: 자동
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351611"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="ce459-102">Auto(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce459-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="ce459-103">선언 되는 외부 프로시저의 외부 이름을 기반으로 .NET Framework 규칙에 따라 문자열을 마샬링하 Visual Basic 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ce459-104">프로젝트 외부에서 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="ce459-105">이 정보에는 프로시저가 있는 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용 하는 문자열 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ce459-106">[Declare 문은](../../../visual-basic/language-reference/statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ce459-107">`Declare` 문의 `charsetmodifier` 부분은 외부 프로시저를 호출 하는 동안 문자열을 마샬링하기 위한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="ce459-108">외부 파일에서 외부 프로시저 이름을 검색 Visual Basic는 방법에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ce459-109">`Auto` 한정자는 Visual Basic .NET Framework 규칙에 따라 문자열을 마샬링하고 런타임 플랫폼의 기본 문자 집합을 결정 하 고 초기 검색에 실패 하는 경우 외부 프로시저 이름을 수정 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="ce459-110">자세한 내용은 [Declare 문의](../../../visual-basic/language-reference/statements/declare-statement.md)"Character Sets"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce459-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="ce459-111">문자 집합 한정자가 지정 되지 않은 경우 `Ansi` 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce459-112">주의</span><span class="sxs-lookup"><span data-stu-id="ce459-112">Remarks</span></span>  
 <span data-ttu-id="ce459-113">이 컨텍스트에서는 `Auto` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ce459-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="ce459-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ce459-115">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="ce459-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ce459-116">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce459-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce459-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce459-117">See also</span></span>

- [<span data-ttu-id="ce459-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="ce459-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="ce459-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="ce459-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="ce459-120">키워드</span><span class="sxs-lookup"><span data-stu-id="ce459-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
