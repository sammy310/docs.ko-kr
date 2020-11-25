---
title: ICorDebugChain::GetPrevious 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
ms.openlocfilehash: 326e170fa98c9e365f9b68bedb585f547ca207ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727707"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="c95e4-102">ICorDebugChain::GetPrevious 메서드</span><span class="sxs-lookup"><span data-stu-id="c95e4-102">ICorDebugChain::GetPrevious Method</span></span>

<span data-ttu-id="c95e4-103">스레드에 대 한 이전 프레임 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c95e4-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="c95e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c95e4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c95e4-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="c95e4-106">제한이 이 스레드에 대 한 이전 프레임 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c95e4-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="c95e4-107">이 체인이 첫 번째 체인이 면 `ppChain` 가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c95e4-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c95e4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c95e4-108">Requirements</span></span>  

 <span data-ttu-id="c95e4-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c95e4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c95e4-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c95e4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c95e4-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c95e4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c95e4-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c95e4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
