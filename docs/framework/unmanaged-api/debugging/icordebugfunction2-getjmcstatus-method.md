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
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137813"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="2315e-102">ICorDebugFunction2::GetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="2315e-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="2315e-103">이 ICorDebugFunction2 개체가 나타내는 함수가 사용자 코드로 표시 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2315e-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2315e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2315e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2315e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2315e-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="2315e-106">제한이 이 함수가 사용자 코드로 표시 되는 경우 `true`되는 부울 값에 대 한 포인터입니다. 그렇지 않으면 값이 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="2315e-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2315e-107">주의</span><span class="sxs-lookup"><span data-stu-id="2315e-107">Remarks</span></span>  
 <span data-ttu-id="2315e-108">이 `ICorDebugFunction2` 표시 하는 함수를 디버그할 수 없는 경우 `pbIsJustMyCode` 항상 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="2315e-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2315e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2315e-109">Requirements</span></span>  
 <span data-ttu-id="2315e-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2315e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2315e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2315e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2315e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2315e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2315e-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2315e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
