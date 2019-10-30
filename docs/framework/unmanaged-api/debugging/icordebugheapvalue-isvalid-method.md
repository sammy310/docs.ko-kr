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
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138406"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="e5731-102">ICorDebugHeapValue::IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="e5731-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="e5731-103">이 ICorDebugHeapValue 나타내는 개체가 유효한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="e5731-104">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5731-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5731-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5731-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5731-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="e5731-107">제한이 힙의이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5731-108">주의</span><span class="sxs-lookup"><span data-stu-id="e5731-108">Remarks</span></span>  
 <span data-ttu-id="e5731-109">가비지 수집기에서 회수 한 값이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="e5731-110">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-110">This method has been deprecated.</span></span> <span data-ttu-id="e5731-111">.NET Framework 2.0에서 모든 값은 [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 가 호출 될 때까지 유효 하며, 이때 값이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5731-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5731-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5731-112">Requirements</span></span>  
 <span data-ttu-id="e5731-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5731-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5731-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5731-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5731-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5731-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5731-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5731-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
