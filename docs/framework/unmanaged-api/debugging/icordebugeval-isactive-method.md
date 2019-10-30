---
title: ICorDebugEval::IsActive 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: bd10af53d7803964ed6e699ce5328aa8a860216c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085016"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="e813e-102">ICorDebugEval::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="e813e-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="e813e-103">이 ICorDebugEval 개체가 현재 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e813e-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e813e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e813e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e813e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e813e-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="e813e-106">제한이 이 평가가 활성 상태 인지 여부를 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e813e-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e813e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e813e-107">Requirements</span></span>  
 <span data-ttu-id="e813e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e813e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e813e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e813e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e813e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e813e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e813e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e813e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
