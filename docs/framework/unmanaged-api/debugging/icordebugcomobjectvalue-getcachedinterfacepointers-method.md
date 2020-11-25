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
ms.openlocfilehash: c3120a0dd859f581e6356fc260043cb83250ae9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724834"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="b0146-102">ICorDebugComObjectValue::GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="b0146-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>

<span data-ttu-id="b0146-103">현재 RCW (런타임 호출 가능 래퍼)에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0146-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0146-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0146-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0146-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0146-105">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="b0146-106">진행 메서드가 `IInspectable` RCW (런타임 호출 가능 래퍼)에 의해 캐시 된 인터페이스 (인터페이스) 또는 모든 COM 인터페이스만 Windows 런타임 반환 하는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b0146-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="b0146-107">진행 주소를 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0146-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b0146-108">제한이 `CORDB_ADDRESS` 에 실제로 반환 된 값 수에 대 한 포인터 `ptrs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b0146-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="b0146-109">`CORDB_ADDRESS`캐시 된 인터페이스 개체의 주소를 포함 하는 값 배열의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0146-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0146-110">설명</span><span class="sxs-lookup"><span data-stu-id="b0146-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0146-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0146-111">Requirements</span></span>  

 <span data-ttu-id="b0146-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0146-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0146-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0146-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0146-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0146-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0146-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0146-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0146-116">참조</span><span class="sxs-lookup"><span data-stu-id="b0146-116">See also</span></span>

- [<span data-ttu-id="b0146-117">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0146-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="b0146-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0146-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
