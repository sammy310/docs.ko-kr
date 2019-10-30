---
title: ICorDebugProcess8 인터페이스
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
ms.openlocfilehash: dc7de361386b9ee21d6cf05c36a7f63c3e1c25f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123365"
---
# <a name="icordebugprocess8-interface"></a><span data-ttu-id="9d79a-102">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d79a-102">ICorDebugProcess8 Interface</span></span>
<span data-ttu-id="9d79a-103">[.NET Framework 4.6 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="9d79a-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="9d79a-104">ICorDebugProcess 인터페이스를 논리적으로 확장 하 여 특정 형식의 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d79a-104">Logically extends the ICorDebugProcess interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d79a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9d79a-105">Methods</span></span>  
  
|<span data-ttu-id="9d79a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9d79a-106">Method</span></span>|<span data-ttu-id="9d79a-107">설명</span><span class="sxs-lookup"><span data-stu-id="9d79a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d79a-108">EnableExceptionCallbacksOutsideOfMyCode 메서드</span><span class="sxs-lookup"><span data-stu-id="9d79a-108">EnableExceptionCallbacksOutsideOfMyCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|<span data-ttu-id="9d79a-109">특정 형식의 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d79a-109">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d79a-110">주의</span><span class="sxs-lookup"><span data-stu-id="9d79a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d79a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d79a-111">Requirements</span></span>  
 <span data-ttu-id="9d79a-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d79a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d79a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d79a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d79a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d79a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d79a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d79a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d79a-116">참조</span><span class="sxs-lookup"><span data-stu-id="9d79a-116">See also</span></span>

- [<span data-ttu-id="9d79a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d79a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9d79a-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="9d79a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
