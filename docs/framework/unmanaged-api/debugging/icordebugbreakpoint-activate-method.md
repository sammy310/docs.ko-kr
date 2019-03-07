---
title: ICorDebugBreakpoint::Activate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac37df58762dac4e3a6161361cafd8ea87e2657
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491362"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="d25ce-102">ICorDebugBreakpoint::Activate 메서드</span><span class="sxs-lookup"><span data-stu-id="d25ce-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="d25ce-103">이 활성 상태를 설정 `ICorDebugBreakpoint`합니다.</span><span class="sxs-lookup"><span data-stu-id="d25ce-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="d25ce-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d25ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d25ce-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="d25ce-106">[in] 이 값을 설정 `true` 활성;으로 상태를 지정 하 그렇지 않은 경우이 값을 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d25ce-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25ce-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d25ce-107">Requirements</span></span>  
 <span data-ttu-id="d25ce-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d25ce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25ce-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d25ce-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d25ce-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d25ce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d25ce-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d25ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
