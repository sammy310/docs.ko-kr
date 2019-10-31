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
ms.openlocfilehash: 2e49dd95cf5d78c0a0f4fa075126eca19dea2693
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138709"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="37c87-102">ICorDebugThread2::GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="37c87-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="37c87-103">이 ICorDebugThread2에 대 한 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37c87-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37c87-104">구문</span><span class="sxs-lookup"><span data-stu-id="37c87-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37c87-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37c87-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="37c87-106">제한이 이 스레드에 대 한 운영 체제 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="37c87-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37c87-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37c87-107">Requirements</span></span>  
 <span data-ttu-id="37c87-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c87-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37c87-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37c87-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37c87-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37c87-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37c87-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37c87-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
