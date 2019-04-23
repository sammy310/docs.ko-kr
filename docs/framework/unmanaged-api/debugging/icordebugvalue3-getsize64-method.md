---
title: ICorDebugValue3::GetSize64 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c0b45e08f7b88d9374023f95c6e3e22139c8949
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144770"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="502e6-102">ICorDebugValue3::GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="502e6-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="502e6-103">이 바이트 단위로 크기를 가져옵니다 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="502e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="502e6-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="502e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="502e6-105">Parameters</span></span>  
 <span data-ttu-id="502e6-106">pSize</span><span class="sxs-lookup"><span data-stu-id="502e6-106">pSize</span></span>  
 <span data-ttu-id="502e6-107">[out] 이 개체를 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="502e6-108">설명</span><span class="sxs-lookup"><span data-stu-id="502e6-108">Remarks</span></span>  
 <span data-ttu-id="502e6-109">이 값 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아닌 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="502e6-110">`ICorDebugValue3::GetSize` 에서 다른 메서드를 [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) 메서드 출력 매개 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="502e6-111">[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), 출력 매개 변수가 `ULONG32`; `ICorDebugValue3::GetSize`, 것을 `ULONG64`입니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="502e6-112">그러면 합니다 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 2GB를 초과 하는 배열 크기를 보고 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="502e6-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="502e6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="502e6-113">Requirements</span></span>  
 <span data-ttu-id="502e6-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="502e6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="502e6-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="502e6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="502e6-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="502e6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="502e6-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="502e6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="502e6-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="502e6-118">See also</span></span>

- [<span data-ttu-id="502e6-119">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502e6-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="502e6-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502e6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
