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
ms.openlocfilehash: 9fddee70e34ba9bf7c1860c1a160db369e45fb5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698165"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="db678-102">ICorDebugArrayValue::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="db678-102">ICorDebugArrayValue::GetRank Method</span></span>

<span data-ttu-id="db678-103">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="db678-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db678-104">구문</span><span class="sxs-lookup"><span data-stu-id="db678-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db678-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db678-105">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="db678-106">제한이 이 개체의 차원 수에 대 한 포인터 `ICorDebugArrayValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="db678-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db678-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db678-107">Requirements</span></span>  

 <span data-ttu-id="db678-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db678-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db678-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db678-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db678-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db678-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db678-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db678-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
