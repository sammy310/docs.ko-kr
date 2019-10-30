---
title: ICorDebugGenericValue::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 7923008eecb9011bead685fbbb7f05f81f12329b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138587"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="43384-102">ICorDebugGenericValue::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="43384-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="43384-103">이 제네릭의 값을 지정 된 버퍼에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="43384-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43384-104">구문</span><span class="sxs-lookup"><span data-stu-id="43384-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43384-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43384-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="43384-106">제한이 이 ICorDebugGenericValue 개체가 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="43384-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="43384-107">값은 단순 형식 또는 참조 형식 (즉, 포인터) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43384-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43384-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43384-108">Requirements</span></span>  
 <span data-ttu-id="43384-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43384-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43384-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43384-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43384-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43384-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43384-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43384-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
