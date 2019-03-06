---
title: ICorDebugChain::GetThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ab2b584b4a3e9bef17110f3084dc93efb2e5167
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481653"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="cd6e3-102">ICorDebugChain::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="cd6e3-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="cd6e3-103">이 호출 체인은 실제 스레드에서의 부분을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd6e3-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd6e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd6e3-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd6e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd6e3-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="cd6e3-106">[out] 실제 스레드에 나타내는 ICorDebugThread 개체에 대 한 포인터가 호출 체인의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cd6e3-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd6e3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd6e3-107">Requirements</span></span>  
 <span data-ttu-id="cd6e3-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd6e3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6e3-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd6e3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd6e3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd6e3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd6e3-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
