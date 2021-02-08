---
description: '자세히 알아보기: Auto (Visual Basic)'
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
ms.openlocfilehash: 9601b6c253d4366c453950b4d8f3c5b2caf3805f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774683"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="a46b2-103">Auto(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a46b2-103">Auto (Visual Basic)</span></span>

<span data-ttu-id="a46b2-104">선언 되는 외부 프로시저의 외부 이름을 기반으로 .NET Framework 규칙에 따라 문자열을 마샬링하 Visual Basic 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-104">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="a46b2-105">프로젝트 외부에서 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-105">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="a46b2-106">이 정보에는 프로시저가 있는 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용 하는 문자열 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-106">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="a46b2-107">[Declare 문은](../statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-107">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="a46b2-108">`charsetmodifier` `Declare` 문의 부분은 외부 프로시저를 호출 하는 동안 문자열을 마샬링하기 위한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-108">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="a46b2-109">외부 파일에서 외부 프로시저 이름을 검색 Visual Basic는 방법에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-109">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="a46b2-110">`Auto`한정자는 Visual Basic에서 .NET Framework 규칙에 따라 문자열을 마샬링하고 런타임 플랫폼의 기본 문자 집합을 결정 하 고 초기 검색에 실패 하는 경우 외부 프로시저 이름을 수정 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-110">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="a46b2-111">자세한 내용은 [Declare 문의](../statements/declare-statement.md)"Character Sets"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a46b2-111">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="a46b2-112">문자 집합 한정자가 지정 되지 않은 경우 `Ansi` 가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-112">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a46b2-113">설명</span><span class="sxs-lookup"><span data-stu-id="a46b2-113">Remarks</span></span>  

 <span data-ttu-id="a46b2-114">`Auto`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-114">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a46b2-115">Declare 문</span><span class="sxs-lookup"><span data-stu-id="a46b2-115">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="a46b2-116">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="a46b2-116">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="a46b2-117">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a46b2-117">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46b2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a46b2-118">See also</span></span>

- [<span data-ttu-id="a46b2-119">Ansi</span><span class="sxs-lookup"><span data-stu-id="a46b2-119">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="a46b2-120">유니코드</span><span class="sxs-lookup"><span data-stu-id="a46b2-120">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="a46b2-121">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="a46b2-121">Keywords</span></span>](../keywords/index.md)
