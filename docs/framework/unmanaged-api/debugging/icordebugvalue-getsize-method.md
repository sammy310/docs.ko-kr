---
title: ICorDebugValue::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d26ddb6d89af60acf6dc1214b0423ba75e488ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791160"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="6368d-102">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="6368d-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="6368d-103">이 "ICorDebugValue" 개체의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6368d-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6368d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6368d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6368d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6368d-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="6368d-106">제한이 이 값 개체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="6368d-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6368d-107">주의</span><span class="sxs-lookup"><span data-stu-id="6368d-107">Remarks</span></span>  
 <span data-ttu-id="6368d-108">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6368d-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="6368d-109">`ICorDebugValue::GetSize` 메서드는 64 비트 플랫폼에서 4gb 보다 큰 개체에 대 한 `COR_E_OVERFLOW`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6368d-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="6368d-110">4gb 보다 큰 개체에 대해 [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6368d-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6368d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6368d-111">Requirements</span></span>  
 <span data-ttu-id="6368d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6368d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6368d-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6368d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6368d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6368d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6368d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6368d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6368d-116">참조</span><span class="sxs-lookup"><span data-stu-id="6368d-116">See also</span></span>

- [<span data-ttu-id="6368d-117">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="6368d-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
