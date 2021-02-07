---
description: '자세히 알아보기: ICorDebugComObjectValue:: Getcachedclassid 포인터 메서드'
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
ms.openlocfilehash: 737d71f6aa903a3dfa97f583b47a322ec074147f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710857"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="579e5-103">ICorDebugComObjectValue::GetCachedInterfacePointers 메서드</span><span class="sxs-lookup"><span data-stu-id="579e5-103">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>

<span data-ttu-id="579e5-104">현재 RCW (런타임 호출 가능 래퍼)에 캐시 된 원시 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="579e5-104">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="579e5-105">구문</span><span class="sxs-lookup"><span data-stu-id="579e5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="579e5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="579e5-106">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="579e5-107">진행 메서드가 `IInspectable` RCW (런타임 호출 가능 래퍼)에 의해 캐시 된 인터페이스 (인터페이스) 또는 모든 COM 인터페이스만 Windows 런타임 반환 하는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="579e5-107">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="579e5-108">진행 주소를 검색할 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="579e5-108">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="579e5-109">제한이 `CORDB_ADDRESS` 에 실제로 반환 된 값 수에 대 한 포인터 `ptrs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="579e5-109">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="579e5-110">`CORDB_ADDRESS`캐시 된 인터페이스 개체의 주소를 포함 하는 값 배열의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="579e5-110">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="579e5-111">설명</span><span class="sxs-lookup"><span data-stu-id="579e5-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="579e5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="579e5-112">Requirements</span></span>  

 <span data-ttu-id="579e5-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="579e5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="579e5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="579e5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="579e5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="579e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="579e5-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="579e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579e5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="579e5-117">See also</span></span>

- [<span data-ttu-id="579e5-118">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="579e5-118">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="579e5-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="579e5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
