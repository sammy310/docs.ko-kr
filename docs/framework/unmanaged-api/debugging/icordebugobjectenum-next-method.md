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
ms.openlocfilehash: e9b32980a5606629676549905d3c9956633f25b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178696"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="8f346-102">ICorDebugObjectEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="8f346-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="8f346-103">현재 위치에서 시작하여 열거형에서 지정된 수의 개체 수의 상대 가상 주소(RAS)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f346-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f346-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f346-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f346-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f346-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8f346-106">[in] 검색할 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f346-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="8f346-107">【아웃】 CORDB_ADDRESS 개체를 가리키는 각각의 포인터 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f346-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8f346-108">【아웃】 실제로 반환된 개체 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f346-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="8f346-109">이 `celt` 값은 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f346-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f346-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f346-110">Requirements</span></span>  
 <span data-ttu-id="8f346-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f346-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f346-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f346-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f346-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f346-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f346-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f346-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f346-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f346-115">See also</span></span>
