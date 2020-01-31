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
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791097"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="07e23-102">ICorDebugValue3::GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="07e23-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="07e23-103">이 [ICorDebugValue3](icordebugvalue3-interface.md) 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e23-104">구문</span><span class="sxs-lookup"><span data-stu-id="07e23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07e23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07e23-105">Parameters</span></span>  
 <span data-ttu-id="07e23-106">pSize</span><span class="sxs-lookup"><span data-stu-id="07e23-106">pSize</span></span>  
 <span data-ttu-id="07e23-107">제한이 이 개체의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07e23-108">주의</span><span class="sxs-lookup"><span data-stu-id="07e23-108">Remarks</span></span>  
 <span data-ttu-id="07e23-109">이 값의 형식이 참조 형식이 면이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="07e23-110">`ICorDebugValue3::GetSize` 메서드는 출력 매개 변수 형식의 [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) 메서드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="07e23-111">[ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md)에서 출력 매개 변수는 `ULONG32`입니다. `ICorDebugValue3::GetSize`에서는 `ULONG64`입니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="07e23-112">이렇게 하면 [ICorDebugValue3](icordebugvalue3-interface.md) 인터페이스가 2gb를 초과 하는 배열의 크기를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07e23-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e23-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07e23-113">Requirements</span></span>  
 <span data-ttu-id="07e23-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07e23-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e23-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07e23-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07e23-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07e23-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07e23-117">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e23-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e23-118">참조</span><span class="sxs-lookup"><span data-stu-id="07e23-118">See also</span></span>

- [<span data-ttu-id="07e23-119">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07e23-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="07e23-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07e23-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
