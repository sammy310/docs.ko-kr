---
description: '자세히 알아보기: ICorDebugChain:: GetCaller 메서드'
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
ms.openlocfilehash: 5af2132b7fec9e70704db980b95221db6eb273f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695023"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="d698e-103">ICorDebugChain::GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="d698e-103">ICorDebugChain::GetCaller Method</span></span>

<span data-ttu-id="d698e-104">이 체인을 호출한 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d698e-104">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d698e-105">구문</span><span class="sxs-lookup"><span data-stu-id="d698e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d698e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d698e-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="d698e-107">제한이 호출 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d698e-107">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="d698e-108">이 체인이 나 디버거가 호출 스택을 초기화 한 경우와 마찬가지로이 체인이 임의로 호출 된 경우는 null이 됩니다 `ppChain` .</span><span class="sxs-lookup"><span data-stu-id="d698e-108">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d698e-109">설명</span><span class="sxs-lookup"><span data-stu-id="d698e-109">Remarks</span></span>  

 <span data-ttu-id="d698e-110">호출이 스레드 간에 마샬링된 경우 호출 체인이 다른 스레드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d698e-110">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d698e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d698e-111">Requirements</span></span>  

 <span data-ttu-id="d698e-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d698e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d698e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d698e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d698e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d698e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d698e-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d698e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
