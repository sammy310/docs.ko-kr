---
description: '자세히 알아보기: ICorDebugArrayValue:: GetRank 메서드'
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
ms.openlocfilehash: b84cc8fd49cbb7f7d4aa6fa7fa41b1c6cf8daf29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722999"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="df140-103">ICorDebugArrayValue::GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="df140-103">ICorDebugArrayValue::GetRank Method</span></span>

<span data-ttu-id="df140-104">배열의 차수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df140-104">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df140-105">구문</span><span class="sxs-lookup"><span data-stu-id="df140-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df140-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df140-106">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="df140-107">제한이 이 개체의 차원 수에 대 한 포인터 `ICorDebugArrayValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="df140-107">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df140-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df140-108">Requirements</span></span>  

 <span data-ttu-id="df140-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df140-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df140-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df140-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df140-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df140-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df140-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df140-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
