---
title: ICorDebugArrayValue::GetRank 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 699c65aae205efd5b08f1d163b4ff9a223bbc217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645658"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="591d6-102">ICorDebugArrayValue::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="591d6-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="591d6-103">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="591d6-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="591d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="591d6-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="591d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="591d6-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="591d6-106">[out] 이 차원 수에 대 한 포인터 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="591d6-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="591d6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="591d6-107">Requirements</span></span>  
 <span data-ttu-id="591d6-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="591d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="591d6-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="591d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="591d6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="591d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="591d6-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="591d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
