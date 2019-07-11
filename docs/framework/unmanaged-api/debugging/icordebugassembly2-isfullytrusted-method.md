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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744507"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="3b745-102">ICorDebugAssembly2::IsFullyTrusted 메서드</span><span class="sxs-lookup"><span data-stu-id="3b745-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="3b745-103">여부를 어셈블리에 부여 된 완전 신뢰 런타임 보안 시스템에서 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b745-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b745-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b745-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b745-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b745-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="3b745-106">[out] `true` 어셈블리에 권한이 부여 된 경우 완전 신뢰 런타임 보안 시스템에서이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3b745-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b745-107">설명</span><span class="sxs-lookup"><span data-stu-id="3b745-107">Remarks</span></span>  
 <span data-ttu-id="3b745-108">이 메서드는 HRESULT의 CORDBG_E_NOTREADY 어셈블리에 대 한 보안 정책을 아직 해결 즉, 어셈블리의 코드가 없으면 경우 아직 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b745-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b745-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b745-109">Requirements</span></span>  
 <span data-ttu-id="3b745-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b745-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b745-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b745-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b745-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b745-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b745-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b745-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
