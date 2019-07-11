---
title: ICorDebugValueEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae09b4f1cd069edf81be583c7c4226717736094
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764280"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="9bf67-102">ICorDebugValueEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="9bf67-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="9bf67-103">"ICorDebugValue" 인스턴스 수가 지정 된 현재 위치부터 시작 하는 열거형에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf67-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf67-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bf67-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf67-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bf67-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9bf67-106">[in] 수가 `ICorDebugValue` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf67-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9bf67-107">[out] 각각 가리키는 포인터 배열을 `ICorDebugValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf67-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9bf67-108">[out] 개수에 대 한 포인터 `ICorDebugValue` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9bf67-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="9bf67-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf67-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf67-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bf67-110">Requirements</span></span>  
 <span data-ttu-id="9bf67-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf67-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bf67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bf67-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bf67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bf67-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf67-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9bf67-115">See also</span></span>
