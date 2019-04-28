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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df5bed730211676acc4770c91cc6551bde0179b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645336"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="de6e5-102">ICorDebugBreakpoint::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="de6e5-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="de6e5-103">나타내는 값을 가져옵니다 여부를이 `ICorDebugBreakpoint` 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de6e5-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de6e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="de6e5-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de6e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de6e5-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="de6e5-106">[out] `true` , 그렇지 않으면이 중단점이 있으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="de6e5-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de6e5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de6e5-107">Requirements</span></span>  
 <span data-ttu-id="de6e5-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de6e5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de6e5-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de6e5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de6e5-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de6e5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de6e5-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de6e5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
