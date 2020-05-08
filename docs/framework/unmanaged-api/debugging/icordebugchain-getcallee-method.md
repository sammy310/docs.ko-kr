---
title: ICorDebugChain::GetCallee 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: ba9a4e32216fd6fad285397bfc48fbc54f602b88
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894657"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="1dc7b-102">ICorDebugChain::GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="1dc7b-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="1dc7b-103">이 체인에 의해 호출 된 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1dc7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dc7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1dc7b-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="1dc7b-106">제한이 호출 된 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="1dc7b-107">이 체인이 현재 실행 중인 경우 (즉,이 체인이 반환 될 호출 된 체인을 기다리지 않는 경우) `ppChain` 는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dc7b-108">설명</span><span class="sxs-lookup"><span data-stu-id="1dc7b-108">Remarks</span></span>  
 <span data-ttu-id="1dc7b-109">이 체인은 실행을 다시 시작 하기 전에 호출 된 체인이 반환 될 때까지 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="1dc7b-110">호출 된 체인은 크로스 스레드 마샬링된 호출의 경우 다른 스레드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dc7b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1dc7b-111">Requirements</span></span>  
 <span data-ttu-id="1dc7b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dc7b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dc7b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dc7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dc7b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dc7b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dc7b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dc7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
