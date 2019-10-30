---
title: ICorDebugObjectEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: adcfbf1207ad7895ab55f7e5cf9581905cb826bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096103"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="bad6a-102">ICorDebugObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="bad6a-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="bad6a-103">현재 위치에서 시작 하 여 열거형에서 지정 된 개체 수의 Rva (상대 가상 주소)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bad6a-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="bad6a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bad6a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bad6a-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bad6a-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="bad6a-107">제한이 각각 CORDB_ADDRESS 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bad6a-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bad6a-108">제한이 실제로 반환 되는 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bad6a-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="bad6a-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad6a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad6a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bad6a-110">Requirements</span></span>  
 <span data-ttu-id="bad6a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bad6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad6a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bad6a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bad6a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bad6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bad6a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad6a-115">참조</span><span class="sxs-lookup"><span data-stu-id="bad6a-115">See also</span></span>
