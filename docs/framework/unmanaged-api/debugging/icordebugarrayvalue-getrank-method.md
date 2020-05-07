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
ms.openlocfilehash: e6401731844f2ce7a1d9fec1c94019f763870fe7
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894988"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="71231-102">ICorDebugArrayValue::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="71231-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="71231-103">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71231-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71231-104">구문</span><span class="sxs-lookup"><span data-stu-id="71231-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71231-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71231-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="71231-106">제한이 이 `ICorDebugArrayValue` 개체의 차원 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="71231-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71231-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71231-107">Requirements</span></span>  
 <span data-ttu-id="71231-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71231-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71231-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71231-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71231-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71231-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71231-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71231-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
