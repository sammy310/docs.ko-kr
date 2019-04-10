---
title: ICorDebugValue2::GetExactType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 002e53d380140a63297a90baa270b5a6f1e5e328
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192266"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="02ca7-102">ICorDebugValue2::GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="02ca7-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="02ca7-103">인터페이스 포인터를 나타내는 "ICorDebugType" 개체를 가져옵니다는 <xref:System.Type> 이 값의 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ca7-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ca7-104">구문</span><span class="sxs-lookup"><span data-stu-id="02ca7-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ca7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02ca7-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="02ca7-106">[out] 주소에 대 한 포인터를 `ICorDebugType` 나타내는 개체를 <xref:System.Type> 이 "ICorDebugValue2" 개체를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02ca7-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02ca7-107">설명</span><span class="sxs-lookup"><span data-stu-id="02ca7-107">Remarks</span></span>  
 <span data-ttu-id="02ca7-108">제네릭 인식 `GetExactType` 메서드를 둘 다 대체를 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 하며 [icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) 메서드를 각 값의 형식에 대 한 정보는 반환 .</span><span class="sxs-lookup"><span data-stu-id="02ca7-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ca7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02ca7-109">Requirements</span></span>  
 <span data-ttu-id="02ca7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02ca7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ca7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02ca7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02ca7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ca7-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="02ca7-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="02ca7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02ca7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="02ca7-114">See also</span></span>
