---
title: ICorDebugThread2::GetVolatileOSThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9bf96371798b38bc392bc6bbd8f6fe8f97c7969
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946312"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="97f3e-102">ICorDebugThread2::GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="97f3e-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="97f3e-103">이 ICorDebugThread2이에 대 한 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97f3e-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="97f3e-104">Syntax</span></span>  
  
```  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97f3e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97f3e-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="97f3e-106">[out] 이 스레드에 대 한 운영 체제 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="97f3e-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f3e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97f3e-107">Requirements</span></span>  
 <span data-ttu-id="97f3e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="97f3e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f3e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97f3e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97f3e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f3e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97f3e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f3e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
