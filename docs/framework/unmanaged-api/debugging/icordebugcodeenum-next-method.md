---
title: ICorDebugCodeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3aeae294d92a6dc9effc7f3baa51a35e4f2b544
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476635"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="57024-102">ICorDebugCodeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="57024-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="57024-103">현재 위치부터 시작 하는 열거형에서 "ICorDebugCode" 인스턴스의 지정 된 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57024-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57024-104">구문</span><span class="sxs-lookup"><span data-stu-id="57024-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57024-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57024-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="57024-106">[in] 수가 `ICorDebugCode` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57024-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="57024-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugCode` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="57024-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="57024-108">[out] 개수에 대 한 포인터 `ICorDebugCode` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="57024-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="57024-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="57024-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57024-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57024-110">Requirements</span></span>  
 <span data-ttu-id="57024-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="57024-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57024-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57024-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57024-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57024-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57024-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57024-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57024-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="57024-115">See also</span></span>


