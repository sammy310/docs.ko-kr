---
title: ICorDebugValue3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140211"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="900ce-102">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="900ce-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="900ce-103">"ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 하 여 2gb 보다 큰 배열에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ce-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="900ce-104">메서드</span><span class="sxs-lookup"><span data-stu-id="900ce-104">Methods</span></span>  
  
|<span data-ttu-id="900ce-105">메서드</span><span class="sxs-lookup"><span data-stu-id="900ce-105">Method</span></span>|<span data-ttu-id="900ce-106">설명</span><span class="sxs-lookup"><span data-stu-id="900ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="900ce-107">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="900ce-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="900ce-108">이 `ICorDebugValue3` 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="900ce-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="900ce-109">주의</span><span class="sxs-lookup"><span data-stu-id="900ce-109">Remarks</span></span>  
 <span data-ttu-id="900ce-110">[ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드는 0 바이트에서 2147483647 바이트 범위의 개체 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ce-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="900ce-111">.NET Framework 4.5에서 배열의 크기는 2gb를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ce-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="900ce-112">`ICorDebugValue3` 인터페이스를 사용 하면 이러한 배열의 크기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ce-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="900ce-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="900ce-113">Requirements</span></span>  
 <span data-ttu-id="900ce-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="900ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900ce-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="900ce-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="900ce-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="900ce-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="900ce-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900ce-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900ce-118">참조</span><span class="sxs-lookup"><span data-stu-id="900ce-118">See also</span></span>

- [<span data-ttu-id="900ce-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="900ce-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="900ce-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="900ce-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
