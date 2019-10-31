---
title: ICorDebugChain::GetCaller 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: 5a07550d44857526e8ab4ded9f1827ef12e3bba4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192141"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="1eba8-102">ICorDebugChain::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba8-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="1eba8-103">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1eba8-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eba8-104">구문</span><span class="sxs-lookup"><span data-stu-id="1eba8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eba8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1eba8-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="1eba8-106">제한이 호출 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1eba8-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="1eba8-107">이 체인이 나 디버거가 호출 스택을 초기화 한 경우와 마찬가지로이 체인이 정상적으로 호출 되 면 `ppChain` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba8-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eba8-108">주의</span><span class="sxs-lookup"><span data-stu-id="1eba8-108">Remarks</span></span>  
 <span data-ttu-id="1eba8-109">호출이 스레드 간에 마샬링된 경우 호출 체인이 다른 스레드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eba8-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eba8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eba8-110">Requirements</span></span>  
 <span data-ttu-id="1eba8-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eba8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eba8-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1eba8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1eba8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eba8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eba8-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eba8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
