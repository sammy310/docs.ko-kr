---
title: ICorDebugAppDomain4 인터페이스
ms.date: 03/30/2017
ms.assetid: c536b9dc-148e-4924-bde1-1daa98d49d90
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6077f16f07c5f1fc76b6525ccb036aa1e4fa06
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099302"
---
# <a name="icordebugappdomain4-interface"></a><span data-ttu-id="d3a50-102">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3a50-102">ICorDebugAppDomain4 Interface</span></span>
<span data-ttu-id="d3a50-103">관리 되는 개체를 COM 호출 가능 래퍼를 활용 하려면 ICorDebugAppDomain 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3a50-103">Logically extends the ICorDebugAppDomain interface to get a managed object from a COM callable wrapper.</span></span>  
  
## <a name="method"></a><span data-ttu-id="d3a50-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d3a50-104">Method</span></span>  
  
|<span data-ttu-id="d3a50-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d3a50-105">Method</span></span>|<span data-ttu-id="d3a50-106">설명</span><span class="sxs-lookup"><span data-stu-id="d3a50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3a50-107">GetObjectForCCW 메서드</span><span class="sxs-lookup"><span data-stu-id="d3a50-107">GetObjectForCCW Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-getobjectforccw-method.md)|<span data-ttu-id="d3a50-108">CCW(COM 호출 가능 래퍼) 포인터에서 관리되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3a50-108">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3a50-109">설명</span><span class="sxs-lookup"><span data-stu-id="d3a50-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3a50-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3a50-110">Requirements</span></span>  
 <span data-ttu-id="d3a50-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3a50-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a50-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3a50-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3a50-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3a50-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3a50-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d3a50-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3a50-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3a50-115">See also</span></span>

- [<span data-ttu-id="d3a50-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3a50-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d3a50-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="d3a50-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
