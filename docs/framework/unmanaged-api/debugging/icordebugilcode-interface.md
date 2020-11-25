---
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
ms.openlocfilehash: 980e97dd8ec4792e35bb8c7fbbc2091e9ced719a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728656"
---
# <a name="icordebugilcode-interface"></a><span data-ttu-id="4cba0-102">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cba0-102">ICorDebugILCode Interface</span></span>

<span data-ttu-id="4cba0-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="4cba0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4cba0-104">IL(중간 언어) 코드 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-104">Represents a segment of intermediate language (IL) code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4cba0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4cba0-105">Methods</span></span>  
  
|<span data-ttu-id="4cba0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4cba0-106">Method</span></span>|<span data-ttu-id="4cba0-107">설명</span><span class="sxs-lookup"><span data-stu-id="4cba0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4cba0-108">GetEHClauses 메서드</span><span class="sxs-lookup"><span data-stu-id="4cba0-108">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)|<span data-ttu-id="4cba0-109">이 IL에 대해 정의된 EH(예외 처리) 절 목록에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4cba0-109">Returns a pointer to a list of exception handling (EH) clauses that are defined for this IL.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cba0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cba0-110">Requirements</span></span>  

 <span data-ttu-id="4cba0-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cba0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cba0-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cba0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cba0-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cba0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cba0-114">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cba0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cba0-115">참조</span><span class="sxs-lookup"><span data-stu-id="4cba0-115">See also</span></span>

- [<span data-ttu-id="4cba0-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cba0-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4cba0-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="4cba0-117">Debugging</span></span>](index.md)
