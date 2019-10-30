---
title: ICorDebugBreakpoint::IsActive 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 8df4e1df7836f340bb04fc47d1ca55e0fb7c9f0e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122765"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="791e7-102">ICorDebugBreakpoint::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="791e7-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="791e7-103">이 `ICorDebugBreakpoint` 활성화 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="791e7-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="791e7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="791e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="791e7-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="791e7-106">[out]이 중단점이 활성화 되어 있으면 `true`이 고, 그렇지 않으면입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="791e7-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791e7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="791e7-107">Requirements</span></span>  
 <span data-ttu-id="791e7-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="791e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="791e7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="791e7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="791e7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="791e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="791e7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="791e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
