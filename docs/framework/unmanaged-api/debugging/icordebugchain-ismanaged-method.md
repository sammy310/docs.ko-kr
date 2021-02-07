---
description: '자세히 알아보기: ICorDebugChain:: IsManaged 메서드'
title: ICorDebugChain::IsManaged 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: 200b76350d474645a40f8ee35859c2db5420ea0a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694854"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="76486-103">ICorDebugChain::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="76486-103">ICorDebugChain::IsManaged Method</span></span>

<span data-ttu-id="76486-104">이 체인이 관리 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76486-104">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76486-105">구문</span><span class="sxs-lookup"><span data-stu-id="76486-105">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76486-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76486-106">Parameters</span></span>  

 `pManaged`  
 <span data-ttu-id="76486-107">[out] `true` 이 체인이 관리 코드를 실행 하는 경우 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="76486-107">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76486-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76486-108">Requirements</span></span>  

 <span data-ttu-id="76486-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76486-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76486-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76486-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76486-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76486-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76486-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76486-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
