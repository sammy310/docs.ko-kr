---
description: '자세히 알아보기: ICorDebugArrayValue:: GetBaseIndicies 메서드'
title: ICorDebugArrayValue::GetBaseIndicies 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: ac38123860cc3187b7dc2398b32244387d19c5ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723123"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="413fa-103">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="413fa-103">ICorDebugArrayValue::GetBaseIndicies Method</span></span>

<span data-ttu-id="413fa-104">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="413fa-104">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="413fa-105">구문</span><span class="sxs-lookup"><span data-stu-id="413fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="413fa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="413fa-106">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="413fa-107">진행 이 개체의 차원 수입니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="413fa-107">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="413fa-108">이 값은 `indicies` 배열의 크기가 개체의 차원 수와 같으므로 배열의 크기 이기도 합니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="413fa-108">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="413fa-109">제한이 이 개체의 차원에 대 한 기본 인덱스 (즉, 시작 인덱스) 인 정수 배열입니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="413fa-109">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="413fa-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="413fa-110">Requirements</span></span>  

 <span data-ttu-id="413fa-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="413fa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="413fa-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="413fa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="413fa-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="413fa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="413fa-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
