---
description: '자세히 알아보기: ICorDebugChain:: GetThread 메서드'
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
ms.openlocfilehash: 090cb40c3681792ce4a30cd342e65dc02ac3f381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694923"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="3a79a-103">ICorDebugChain::GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="3a79a-103">ICorDebugChain::GetThread Method</span></span>

<span data-ttu-id="3a79a-104">이 호출 체인이 속한 실제 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a79a-104">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a79a-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a79a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a79a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a79a-106">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="3a79a-107">제한이 이 호출 체인이 속한 실제 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a79a-107">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a79a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a79a-108">Requirements</span></span>  

 <span data-ttu-id="3a79a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a79a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a79a-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a79a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a79a-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a79a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a79a-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a79a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
