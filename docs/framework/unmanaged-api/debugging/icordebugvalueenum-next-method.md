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
ms.openlocfilehash: 09394acb07b8595f99d9ecc873eb0985cdd79316
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134592"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="51b29-102">ICorDebugValueEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="51b29-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="51b29-103">현재 위치에서 시작 하 여 열거형에서 지정 된 수의 "ICorDebugValue" 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51b29-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b29-104">구문</span><span class="sxs-lookup"><span data-stu-id="51b29-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51b29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51b29-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="51b29-106">진행 검색할 `ICorDebugValue` 인스턴스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="51b29-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="51b29-107">제한이 각각 `ICorDebugValue` 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="51b29-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="51b29-108">제한이 실제로 반환 된 `ICorDebugValue` 인스턴스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51b29-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="51b29-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b29-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b29-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51b29-110">Requirements</span></span>  
 <span data-ttu-id="51b29-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51b29-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51b29-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51b29-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51b29-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51b29-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51b29-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b29-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b29-115">참조</span><span class="sxs-lookup"><span data-stu-id="51b29-115">See also</span></span>
