---
title: ICorDebugArrayValue::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d00c04f3719d6fb340541d3301d4dc4a3f95ca40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645723"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="58221-102">ICorDebugArrayValue::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="58221-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="58221-103">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58221-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58221-104">구문</span><span class="sxs-lookup"><span data-stu-id="58221-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58221-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58221-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="58221-106">[out] 배열에 있는 요소의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58221-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58221-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58221-107">Requirements</span></span>  
 <span data-ttu-id="58221-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58221-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58221-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58221-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58221-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58221-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58221-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58221-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
