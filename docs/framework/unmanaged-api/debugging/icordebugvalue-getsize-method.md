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
ms.openlocfilehash: 94d8fbf4d93bbfbaaeb7c1268004aada22b9b7df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768918"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="32c14-102">ICorDebugValue::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="32c14-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="32c14-103">이 "ICorDebugValue" 개체를 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32c14-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c14-104">구문</span><span class="sxs-lookup"><span data-stu-id="32c14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32c14-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32c14-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="32c14-106">[out] 이 값 개체의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="32c14-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32c14-107">설명</span><span class="sxs-lookup"><span data-stu-id="32c14-107">Remarks</span></span>  
 <span data-ttu-id="32c14-108">값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아닌 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c14-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="32c14-109">합니다 `ICorDebugValue::GetSize` 메서드가 반환 되는 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c14-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="32c14-110">사용 된 [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 대신 개체에 대 한는 4GB 보다 큰 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c14-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c14-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32c14-111">Requirements</span></span>  
 <span data-ttu-id="32c14-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32c14-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c14-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32c14-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32c14-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32c14-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32c14-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c14-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c14-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="32c14-116">See also</span></span>

- [<span data-ttu-id="32c14-117">GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="32c14-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
