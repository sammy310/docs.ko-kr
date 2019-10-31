---
title: ICorDebugReferenceValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 61563488bff682cc7a417296c3db8eb7e7cf965a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139329"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="7bf2a-102">ICorDebugReferenceValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="7bf2a-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="7bf2a-103">지정 된 메모리 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-103">Sets the specified memory address.</span></span> <span data-ttu-id="7bf2a-104">즉,이 메서드는 개체를 가리키도록이 ICorDebugReferenceValue를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bf2a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bf2a-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="7bf2a-107">진행 이 `ICorDebugReferenceValue` 가리키는 개체의 주소를 지정 하는 `CORDB_ADDRESS` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf2a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bf2a-108">Requirements</span></span>  
 <span data-ttu-id="7bf2a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf2a-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bf2a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bf2a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bf2a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bf2a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf2a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
