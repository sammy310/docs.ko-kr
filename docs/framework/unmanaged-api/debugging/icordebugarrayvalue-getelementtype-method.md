---
title: ICorDebugArrayValue::GetElementType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: d4de3405f84bfc08f7e1519bc7f9604eb1f5a14e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088299"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="123f5-102">ICorDebugArrayValue::GetElementType 메서드</span><span class="sxs-lookup"><span data-stu-id="123f5-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="123f5-103">배열에 있는 요소의 단순 형식을 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="123f5-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="123f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="123f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="123f5-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="123f5-106">제한이 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="123f5-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123f5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="123f5-107">Requirements</span></span>  
 <span data-ttu-id="123f5-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="123f5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="123f5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="123f5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="123f5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="123f5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="123f5-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="123f5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
