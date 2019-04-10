---
title: ICorDebugComObjectValue::GetCachedInterfacePointers 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da0e62250dbef9be93ccee7020e23c3f83e85592
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223279"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="0f0f9-102">ICorDebugComObjectValue::GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="0f0f9-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="0f0f9-103">현재 런타임 호출 가능 래퍼 (RCW)에 캐시 하는 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f0f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f0f9-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f0f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f0f9-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="0f0f9-106">[in] 메서드는만 반환 하는지 여부를 나타내는 값을 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 인터페이스 (`IInspectable` 인터페이스) 또는 런타임 호출 가능 래퍼 (RCW)에 의해 캐시 되는 모든 COM 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-106">[in] A value that indicates whether the method will return only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="0f0f9-107">[in] 해당 주소를 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0f0f9-108">[out] 개수에 대 한 포인터 `CORDB_ADDRESS` 에 실제로 반환 된 값 `ptrs`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="0f0f9-109">배열의 시작 주소에 대 한 포인터 `CORDB_ADDRESS` 캐시 된 인터페이스 개체의 주소를 포함 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f0f9-110">설명</span><span class="sxs-lookup"><span data-stu-id="0f0f9-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f0f9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f0f9-111">Requirements</span></span>  
 <span data-ttu-id="0f0f9-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f0f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f0f9-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f0f9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f0f9-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f0f9-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0f0f9-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0f0f9-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f0f9-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f0f9-116">See also</span></span>

- [<span data-ttu-id="0f0f9-117">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f0f9-117">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="0f0f9-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f0f9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
