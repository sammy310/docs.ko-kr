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
ms.openlocfilehash: 71e32211e6ab16fb5e4e2c624dbad3af5fd6b09f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132023"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="9b1bb-102">ICorDebugObjectValue::IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="9b1bb-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="9b1bb-103">이 개체 값을 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b1bb-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b1bb-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b1bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b1bb-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="9b1bb-106">[out] 부울 값에 대 한 포인터 `true` 는 참조 형식 보다는 값 형식 개체 값이 "ICorDebugObjectValue"를 나타내는 경우이 고, 그렇지 `pbIsValueClass` 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b1bb-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b1bb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b1bb-107">Requirements</span></span>  
 <span data-ttu-id="9b1bb-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b1bb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b1bb-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b1bb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b1bb-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b1bb-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9b1bb-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="9b1bb-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b1bb-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b1bb-112">See also</span></span>
