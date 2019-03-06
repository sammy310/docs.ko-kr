---
title: ICorDebugTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43349dd3562b4480746948a0e65cc52580e377b3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470694"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="0bd79-102">ICorDebugTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0bd79-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="0bd79-103">지정 된 "ICorDebugType" 인스턴스 수를 가져옵니다 `celt` 를 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd79-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd79-104">구문</span><span class="sxs-lookup"><span data-stu-id="0bd79-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bd79-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bd79-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0bd79-106">[in] 수가 `ICorDebugType` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd79-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0bd79-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugType` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd79-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0bd79-108">[out] 개수에 대 한 포인터 `ICorDebugType` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0bd79-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="0bd79-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd79-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd79-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bd79-110">Requirements</span></span>  
 <span data-ttu-id="0bd79-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bd79-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bd79-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bd79-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bd79-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bd79-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bd79-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bd79-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd79-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bd79-115">See also</span></span>

