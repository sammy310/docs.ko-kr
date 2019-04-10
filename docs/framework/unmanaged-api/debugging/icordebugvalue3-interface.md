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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221979"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="9b9bc-102">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b9bc-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="9b9bc-103">2GB 보다 큰 배열 지원 하기 위해 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b9bc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9b9bc-104">Methods</span></span>  
  
|<span data-ttu-id="9b9bc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9b9bc-105">Method</span></span>|<span data-ttu-id="9b9bc-106">설명</span><span class="sxs-lookup"><span data-stu-id="9b9bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b9bc-107">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="9b9bc-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="9b9bc-108">이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue3` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b9bc-109">설명</span><span class="sxs-lookup"><span data-stu-id="9b9bc-109">Remarks</span></span>  
 <span data-ttu-id="9b9bc-110">합니다 [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 범위 개체 크기를 0에서 2,147,483,647 바이트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="9b9bc-111">에 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 배열의 크기는 2GB를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="9b9bc-112">`ICorDebugValue3` 인터페이스를 사용 하면 이러한 배열 크기를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b9bc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b9bc-113">Requirements</span></span>  
 <span data-ttu-id="9b9bc-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b9bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b9bc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b9bc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b9bc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b9bc-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9b9bc-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="9b9bc-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b9bc-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b9bc-118">See also</span></span>

- [<span data-ttu-id="9b9bc-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b9bc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9b9bc-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="9b9bc-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
