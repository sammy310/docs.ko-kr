---
title: ICorDebugValue::GetType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83265c4f6dffed76f1710378cf5293aac7020ef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119355"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="ed59e-102">ICorDebugValue::GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="ed59e-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="ed59e-103">이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed59e-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed59e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed59e-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed59e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed59e-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="ed59e-106">[out] 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed59e-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed59e-107">설명</span><span class="sxs-lookup"><span data-stu-id="ed59e-107">Remarks</span></span>  
 <span data-ttu-id="ed59e-108">개체는 복잡 한 런타임 형식인 경우 해당 형식을의 적절 한 서브 클래스를 통해 검사할 수 있습니다는 `ICorDebugValue` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed59e-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="ed59e-109">예를 들어, "ICorDebugObjectValue"에서 상속 되는 `ICorDebugValue`, 복합 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed59e-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="ed59e-110">합니다 `GetType` 하 고 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 메서드는 각 값의 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed59e-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="ed59e-111">모두를 제네릭 인식으로 대체 [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ed59e-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed59e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed59e-112">Requirements</span></span>  
 <span data-ttu-id="ed59e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed59e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed59e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed59e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed59e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed59e-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ed59e-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="ed59e-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed59e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed59e-117">See also</span></span>
