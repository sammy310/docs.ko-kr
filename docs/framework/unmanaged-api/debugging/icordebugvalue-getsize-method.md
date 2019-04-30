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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a9ff2c94c98a5acc930d68e648b0ea577a82c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986845"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="439ea-102">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="439ea-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="439ea-103">이 "ICorDebugValue" 개체를 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="439ea-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="439ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="439ea-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="439ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="439ea-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="439ea-106">[out] 이 값 개체의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="439ea-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="439ea-107">설명</span><span class="sxs-lookup"><span data-stu-id="439ea-107">Remarks</span></span>  
 <span data-ttu-id="439ea-108">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아닌 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="439ea-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="439ea-109">합니다 `ICorDebugValue::GetSize` 메서드가 반환 되는 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="439ea-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="439ea-110">사용 된 [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 대신 개체에 대 한는 4GB 보다 큰 합니다.</span><span class="sxs-lookup"><span data-stu-id="439ea-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="439ea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="439ea-111">Requirements</span></span>  
 <span data-ttu-id="439ea-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="439ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="439ea-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="439ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="439ea-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="439ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="439ea-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="439ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="439ea-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="439ea-116">See also</span></span>

- [<span data-ttu-id="439ea-117">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="439ea-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
