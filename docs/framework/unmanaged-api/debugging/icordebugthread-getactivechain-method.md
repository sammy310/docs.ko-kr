---
description: '자세히 알아보기: ICorDebugThread:: GetActiveChain 메서드'
title: ICorDebugThread::GetActiveChain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: d9aff80801fa72a227a84b3b5216e3ffa72b0e24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659285"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="15754-103">ICorDebugThread::GetActiveChain 메서드</span><span class="sxs-lookup"><span data-stu-id="15754-103">ICorDebugThread::GetActiveChain Method</span></span>

<span data-ttu-id="15754-104">이 ICorDebugThread 개체의 활성 (가장 최근) 스택 체인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15754-104">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15754-105">구문</span><span class="sxs-lookup"><span data-stu-id="15754-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15754-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15754-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="15754-107">제한이 스택 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15754-107">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15754-108">설명</span><span class="sxs-lookup"><span data-stu-id="15754-108">Remarks</span></span>  

 <span data-ttu-id="15754-109">`ppChain`현재 활성 상태인 스택 체인이 없는 경우 매개 변수는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="15754-109">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15754-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15754-110">Requirements</span></span>  

 <span data-ttu-id="15754-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15754-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15754-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15754-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15754-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15754-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15754-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15754-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
