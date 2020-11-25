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
ms.openlocfilehash: 064f9727b221dd64a58f8cd5e103271e37020786
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730177"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="85303-102">ICorDebugBreakpoint::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="85303-102">ICorDebugBreakpoint::IsActive Method</span></span>

<span data-ttu-id="85303-103">이가 활성 상태 인지 여부를 나타내는 값을 가져옵니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="85303-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85303-104">구문</span><span class="sxs-lookup"><span data-stu-id="85303-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85303-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85303-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="85303-106">[out] `true` 이 중단점이 활성 상태 이면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="85303-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85303-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85303-107">Requirements</span></span>  

 <span data-ttu-id="85303-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85303-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85303-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85303-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85303-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85303-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85303-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85303-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
