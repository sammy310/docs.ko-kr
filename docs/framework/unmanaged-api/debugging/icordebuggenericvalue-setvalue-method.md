---
title: ICorDebugGenericValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756897"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="06b81-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="06b81-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="06b81-103">지정된 된 버퍼에서 새 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="06b81-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b81-104">구문</span><span class="sxs-lookup"><span data-stu-id="06b81-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06b81-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="06b81-106">[in] 값을 복사해 올 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="06b81-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06b81-107">설명</span><span class="sxs-lookup"><span data-stu-id="06b81-107">Remarks</span></span>  
 <span data-ttu-id="06b81-108">참조 형식의 경우 값은 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b81-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b81-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06b81-109">Requirements</span></span>  
 <span data-ttu-id="06b81-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06b81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b81-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06b81-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06b81-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06b81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06b81-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
