---
title: ICorDebugProcess8 인터페이스
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 349e0cf93a981a2c598d02f67978e524a6763728
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948579"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="94399-102">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94399-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="94399-103">[[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="94399-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="94399-104">특정 유형의 사용할지 ICorDebugProcess 인터페이스를 논리적으로 확장 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="94399-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94399-105">메서드</span><span class="sxs-lookup"><span data-stu-id="94399-105">Methods</span></span>  
  
|<span data-ttu-id="94399-106">메서드</span><span class="sxs-lookup"><span data-stu-id="94399-106">Method</span></span>|<span data-ttu-id="94399-107">설명</span><span class="sxs-lookup"><span data-stu-id="94399-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94399-108">EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="94399-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="94399-109">특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="94399-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94399-110">설명</span><span class="sxs-lookup"><span data-stu-id="94399-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94399-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94399-111">Requirements</span></span>  
 <span data-ttu-id="94399-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="94399-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94399-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94399-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94399-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94399-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94399-115">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94399-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94399-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="94399-116">See also</span></span>

- [<span data-ttu-id="94399-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94399-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94399-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="94399-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
