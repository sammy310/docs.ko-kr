---
description: '자세히 알아보기: ICorDebugArrayValue:: GetCount 메서드'
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
ms.openlocfilehash: 7b1422714ed9c6f89c65c310165b8cdaa6566360
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723129"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="fd49c-103">ICorDebugArrayValue::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="fd49c-103">ICorDebugArrayValue::GetCount Method</span></span>

<span data-ttu-id="fd49c-104">배열에 있는 요소의 총 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd49c-104">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd49c-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd49c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd49c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd49c-106">Parameters</span></span>  

 `pnCount`  
 <span data-ttu-id="fd49c-107">제한이 배열에 있는 요소의 총 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd49c-107">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd49c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd49c-108">Requirements</span></span>  

 <span data-ttu-id="fd49c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd49c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd49c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd49c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd49c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd49c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd49c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd49c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
