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
ms.openlocfilehash: 799a7320b701384dc5f4b4b46fef8544f6b15b02
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875507"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="a2b3d-102">Auto(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2b3d-102">Auto (Visual Basic)</span></span>

<span data-ttu-id="a2b3d-103">선언 되는 외부 프로시저의 외부 이름을 기반으로 .NET Framework 규칙에 따라 문자열을 마샬링하 Visual Basic 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="a2b3d-104">프로젝트 외부에서 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="a2b3d-105">이 정보에는 프로시저가 있는 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용 하는 문자열 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="a2b3d-106">[Declare 문은](../statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="a2b3d-107">`charsetmodifier` `Declare` 문의 부분은 외부 프로시저를 호출 하는 동안 문자열을 마샬링하기 위한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="a2b3d-108">외부 파일에서 외부 프로시저 이름을 검색 Visual Basic는 방법에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="a2b3d-109">`Auto`한정자는 Visual Basic에서 .NET Framework 규칙에 따라 문자열을 마샬링하고 런타임 플랫폼의 기본 문자 집합을 결정 하 고 초기 검색에 실패 하는 경우 외부 프로시저 이름을 수정 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="a2b3d-110">자세한 내용은 [Declare 문의](../statements/declare-statement.md)"Character Sets"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="a2b3d-111">문자 집합 한정자가 지정 되지 않은 경우 `Ansi` 가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2b3d-112">설명</span><span class="sxs-lookup"><span data-stu-id="a2b3d-112">Remarks</span></span>  

 <span data-ttu-id="a2b3d-113">`Auto`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a2b3d-114">Declare 문</span><span class="sxs-lookup"><span data-stu-id="a2b3d-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="a2b3d-115">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="a2b3d-115">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="a2b3d-116">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b3d-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b3d-117">참조</span><span class="sxs-lookup"><span data-stu-id="a2b3d-117">See also</span></span>

- [<span data-ttu-id="a2b3d-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="a2b3d-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="a2b3d-119">유니코드</span><span class="sxs-lookup"><span data-stu-id="a2b3d-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="a2b3d-120">키워드</span><span class="sxs-lookup"><span data-stu-id="a2b3d-120">Keywords</span></span>](../keywords/index.md)
