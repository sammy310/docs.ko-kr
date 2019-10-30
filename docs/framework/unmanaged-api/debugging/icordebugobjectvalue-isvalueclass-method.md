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
ms.openlocfilehash: 0682c0786182422587adb976ff6bc2455b9e5cdc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128942"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="523a8-102">ICorDebugObjectValue::IsValueClass 메서드</span><span class="sxs-lookup"><span data-stu-id="523a8-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="523a8-103">이 개체 값이 값 형식 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="523a8-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="523a8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="523a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="523a8-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="523a8-106">제한이 이 "ICorDebugObjectValue"로 표현 되는 개체 값이 참조 형식이 아닌 값 형식인 경우 `true` 되는 부울 값에 대 한 포인터입니다. 그렇지 않으면 `pbIsValueClass` `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="523a8-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="523a8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="523a8-107">Requirements</span></span>  
 <span data-ttu-id="523a8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="523a8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="523a8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="523a8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="523a8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="523a8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="523a8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="523a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523a8-112">참조</span><span class="sxs-lookup"><span data-stu-id="523a8-112">See also</span></span>
