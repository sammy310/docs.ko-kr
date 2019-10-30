---
title: ICorDebugFunction::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
ms.openlocfilehash: 4229d567fc4ced5e3b78b390ced29fb9ea60f93b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137838"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="5002e-102">ICorDebugFunction::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5002e-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="5002e-103">이 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5002e-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5002e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5002e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5002e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5002e-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="5002e-106">제한이 이 함수에 대 한 메타 데이터를 참조 하는 `mdMethodDef` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5002e-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5002e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5002e-107">Requirements</span></span>  
 <span data-ttu-id="5002e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5002e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5002e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5002e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5002e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5002e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5002e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5002e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
