---
title: ICorDebugObjectValue::IsValueClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b08937182797c8e94048d734d65473fad21b85cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766304"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="7f8ac-102">ICorDebugObjectValue::IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="7f8ac-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="7f8ac-103">이 개체 값을 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f8ac-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f8ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f8ac-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f8ac-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f8ac-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="7f8ac-106">[out] 부울 값에 대 한 포인터 `true` 는 참조 형식 보다는 값 형식 개체 값이 "ICorDebugObjectValue"를 나타내는 경우이 고, 그렇지 `pbIsValueClass` 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f8ac-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f8ac-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f8ac-107">Requirements</span></span>  
 <span data-ttu-id="7f8ac-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f8ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f8ac-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f8ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f8ac-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f8ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f8ac-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f8ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8ac-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f8ac-112">See also</span></span>
