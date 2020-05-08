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
ms.openlocfilehash: 28b54026c8743f31a420e164944f60709e2e271b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894367"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="34c13-102">ICorDebugChain::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="34c13-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="34c13-103">이 호출 체인이 속한 실제 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34c13-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c13-104">구문</span><span class="sxs-lookup"><span data-stu-id="34c13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34c13-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34c13-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="34c13-106">제한이 이 호출 체인이 속한 실제 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="34c13-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34c13-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34c13-107">Requirements</span></span>  
 <span data-ttu-id="34c13-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34c13-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c13-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34c13-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34c13-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34c13-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34c13-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34c13-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
