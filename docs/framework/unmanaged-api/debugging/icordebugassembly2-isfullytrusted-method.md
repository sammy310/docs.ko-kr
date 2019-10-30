---
title: ICorDebugAssembly2::IsFullyTrusted 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133960"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="5a5ff-102">ICorDebugAssembly2::IsFullyTrusted 메서드</span><span class="sxs-lookup"><span data-stu-id="5a5ff-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="5a5ff-103">어셈블리에 런타임 보안 시스템에서 완전 신뢰를 부여 했는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a5ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a5ff-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a5ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a5ff-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="5a5ff-106">[out] 런타임 보안 시스템에서 어셈블리에 완전 신뢰가 부여 된 경우 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a5ff-107">주의</span><span class="sxs-lookup"><span data-stu-id="5a5ff-107">Remarks</span></span>  
 <span data-ttu-id="5a5ff-108">어셈블리에 대 한 보안 정책이 아직 확인 되지 않은 경우이 메서드는 CORDBG_E_NOTREADY의 HRESULT를 반환 합니다. 즉, 어셈블리의 코드가 아직 실행 되지 않은 경우에는입니다.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a5ff-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a5ff-109">Requirements</span></span>  
 <span data-ttu-id="5a5ff-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a5ff-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a5ff-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a5ff-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a5ff-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a5ff-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a5ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
