---
title: ICorDebugHeapValue::IsValid 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478767"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="be7ce-102">ICorDebugHeapValue::IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="be7ce-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="be7ce-103">이 ICorDebugHeapValue이 나타내는 개체가 올바른지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="be7ce-104">이 메서드는.NET Framework 버전 2.0에서에서 더 이상 사용 되지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be7ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="be7ce-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be7ce-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be7ce-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="be7ce-107">[out] 힙에서이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be7ce-108">설명</span><span class="sxs-lookup"><span data-stu-id="be7ce-108">Remarks</span></span>  
 <span data-ttu-id="be7ce-109">값을 가비지 수집기에서 회수 된 경우에 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="be7ce-110">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-110">This method has been deprecated.</span></span> <span data-ttu-id="be7ce-111">.NET Framework 2.0에서는 모든 값이 될 때까지 유효 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 이때 값은 유효성을 검사 하지 않습니다.에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be7ce-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be7ce-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be7ce-112">Requirements</span></span>  
 <span data-ttu-id="be7ce-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be7ce-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be7ce-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be7ce-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be7ce-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be7ce-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be7ce-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be7ce-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
