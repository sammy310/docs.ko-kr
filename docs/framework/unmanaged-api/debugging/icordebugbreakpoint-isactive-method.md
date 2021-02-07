---
description: '자세히 알아보기: ICorDebugBreakpoint:: IsActive 메서드'
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
ms.openlocfilehash: 49e98ccc3722c37b3ff5968215ef3f658601ea10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711793"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="27534-103">ICorDebugBreakpoint::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="27534-103">ICorDebugBreakpoint::IsActive Method</span></span>

<span data-ttu-id="27534-104">이가 활성 상태 인지 여부를 나타내는 값을 가져옵니다 `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="27534-104">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27534-105">구문</span><span class="sxs-lookup"><span data-stu-id="27534-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27534-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27534-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="27534-107">[out] `true` 이 중단점이 활성 상태 이면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="27534-107">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27534-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27534-108">Requirements</span></span>  

 <span data-ttu-id="27534-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27534-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27534-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27534-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27534-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27534-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27534-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27534-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
