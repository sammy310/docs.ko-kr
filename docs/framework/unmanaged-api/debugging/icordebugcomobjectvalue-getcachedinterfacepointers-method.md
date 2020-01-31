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
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783958"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="ae703-102">ICorDebugComObjectValue::GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="ae703-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="ae703-103">현재 RCW (런타임 호출 가능 래퍼)에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae703-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae703-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae703-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae703-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="ae703-106">진행 메서드가 RCW (런타임 호출 가능 래퍼)에 의해 캐시 되는 Windows 런타임 인터페이스 (`IInspectable` 인터페이스) 또는 모든 COM 인터페이스만 반환할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="ae703-107">진행 주소를 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ae703-108">제한이 `ptrs`에서 실제로 반환 된 `CORDB_ADDRESS` 값 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="ae703-109">캐시 된 인터페이스 개체의 주소를 포함 하는 `CORDB_ADDRESS` 값 배열의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae703-110">주의</span><span class="sxs-lookup"><span data-stu-id="ae703-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae703-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae703-111">Requirements</span></span>  
 <span data-ttu-id="ae703-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae703-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae703-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae703-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae703-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae703-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae703-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae703-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae703-116">참조</span><span class="sxs-lookup"><span data-stu-id="ae703-116">See also</span></span>

- [<span data-ttu-id="ae703-117">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae703-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="ae703-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae703-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
