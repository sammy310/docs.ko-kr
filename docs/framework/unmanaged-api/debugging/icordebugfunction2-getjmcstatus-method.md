---
title: ICorDebugFunction2::GetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2364c7c47aed1430a86aeee3daabf6b94cbf3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754485"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="7ac91-102">ICorDebugFunction2::GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="7ac91-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="7ac91-103">이 ICorDebugFunction2 개체로 표현 되는 함수를 사용자 코드로 표시 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ac91-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac91-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ac91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ac91-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ac91-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="7ac91-106">[out] 부울 값에 대 한 포인터 `true`이면이 함수는 사용자 코드로 표시 됩니다. 그렇지 않으면 값은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac91-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ac91-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ac91-107">Remarks</span></span>  
 <span data-ttu-id="7ac91-108">이 나타내는 함수 `ICorDebugFunction2` 디버깅할 수 없습니다 `pbIsJustMyCode` 항상 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac91-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac91-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ac91-109">Requirements</span></span>  
 <span data-ttu-id="7ac91-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ac91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac91-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ac91-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ac91-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ac91-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ac91-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
