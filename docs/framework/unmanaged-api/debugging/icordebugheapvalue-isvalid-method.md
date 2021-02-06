---
description: '자세히 알아보기: ICorDebugHeapValue:: IsValid 메서드'
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
ms.openlocfilehash: 27eca844170b31934cd32dad5cf5fccc0b0e324e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660793"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="11432-103">ICorDebugHeapValue::IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="11432-103">ICorDebugHeapValue::IsValid Method</span></span>

<span data-ttu-id="11432-104">이 ICorDebugHeapValue 나타내는 개체가 유효한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11432-104">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="11432-105">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11432-105">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11432-106">구문</span><span class="sxs-lookup"><span data-stu-id="11432-106">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11432-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11432-107">Parameters</span></span>  

 `pbValid`  
 <span data-ttu-id="11432-108">제한이 힙의이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11432-108">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11432-109">설명</span><span class="sxs-lookup"><span data-stu-id="11432-109">Remarks</span></span>  

 <span data-ttu-id="11432-110">가비지 수집기에서 회수 한 값이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11432-110">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="11432-111">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11432-111">This method has been deprecated.</span></span> <span data-ttu-id="11432-112">.NET Framework 2.0에서 모든 값은 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 가 호출 될 때까지 유효 하며, 이때 값이 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11432-112">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11432-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11432-113">Requirements</span></span>  

 <span data-ttu-id="11432-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11432-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11432-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11432-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11432-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11432-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11432-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11432-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
