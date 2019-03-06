---
title: ICorDebugCode::IsIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78f246f90e7e3b7c9fff984092a0b5eefcba5a13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478065"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="f50f1-102">ICorDebugCode::IsIL 메서드</span><span class="sxs-lookup"><span data-stu-id="f50f1-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="f50f1-103">이 "ICorDebugCode" MSIL (Microsoft intermediate language)에서 컴파일된 코드를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f50f1-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="f50f1-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f50f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f50f1-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="f50f1-106">[out] `true` 이 `ICorDebugCode` 이 고, 그렇지 않으면 MSIL에 컴파일된 코드를 나타내는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f50f1-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f50f1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f50f1-107">Requirements</span></span>  
 <span data-ttu-id="f50f1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f50f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f50f1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f50f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f50f1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f50f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f50f1-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f50f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50f1-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="f50f1-112">See also</span></span>

