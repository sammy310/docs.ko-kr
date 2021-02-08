---
description: '자세히 알아보기: ICorDebugILCode 인터페이스'
title: ICorDebugILCode 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 51c4de0c-3813-4142-be25-a85bb84efb90
topic_type:
- apiref
ms.openlocfilehash: 7bf01195f38fd6e046f89e496de3e91e7f8acb33
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803635"
---
# <a name="icordebugilcode-interface"></a><span data-ttu-id="1715f-103">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1715f-103">ICorDebugILCode Interface</span></span>

<span data-ttu-id="1715f-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="1715f-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1715f-105">IL(중간 언어) 코드 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1715f-105">Represents a segment of intermediate language (IL) code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1715f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1715f-106">Methods</span></span>  
  
|<span data-ttu-id="1715f-107">메서드</span><span class="sxs-lookup"><span data-stu-id="1715f-107">Method</span></span>|<span data-ttu-id="1715f-108">설명</span><span class="sxs-lookup"><span data-stu-id="1715f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1715f-109">GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="1715f-109">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)|<span data-ttu-id="1715f-110">이 IL에 대해 정의된 EH(예외 처리) 절 목록에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1715f-110">Returns a pointer to a list of exception handling (EH) clauses that are defined for this IL.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1715f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1715f-111">Requirements</span></span>  

 <span data-ttu-id="1715f-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1715f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1715f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1715f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1715f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1715f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1715f-115">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1715f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1715f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1715f-116">See also</span></span>

- [<span data-ttu-id="1715f-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1715f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1715f-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="1715f-118">Debugging</span></span>](index.md)
