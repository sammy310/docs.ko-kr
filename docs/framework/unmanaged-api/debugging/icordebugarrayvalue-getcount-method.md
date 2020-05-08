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
ms.openlocfilehash: 82f282630a2e31b8c67d43fa0f0b30431a0d6ee4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895053"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="c68f0-102">ICorDebugArrayValue::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c68f0-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="c68f0-103">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c68f0-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="c68f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c68f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c68f0-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="c68f0-106">제한이 배열에 있는 요소의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c68f0-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c68f0-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c68f0-107">Requirements</span></span>  
 <span data-ttu-id="c68f0-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c68f0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c68f0-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c68f0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c68f0-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c68f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c68f0-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c68f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
