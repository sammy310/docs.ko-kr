---
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
ms.openlocfilehash: ea5c5a728afb9ac90f8599c833caab11fd0c65fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731464"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="fc39f-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="fc39f-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>

<span data-ttu-id="fc39f-103">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc39f-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc39f-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc39f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc39f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc39f-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="fc39f-106">진행 이 개체의 차원 수입니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="fc39f-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="fc39f-107">이 값은 `indicies` 배열의 크기가 개체의 차원 수와 같으므로 배열의 크기 이기도 합니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="fc39f-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="fc39f-108">제한이 이 개체의 차원에 대 한 기본 인덱스 (즉, 시작 인덱스) 인 정수 배열입니다 `ICorDebugArrayValue` .</span><span class="sxs-lookup"><span data-stu-id="fc39f-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc39f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc39f-109">Requirements</span></span>  

 <span data-ttu-id="fc39f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc39f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc39f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc39f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc39f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc39f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc39f-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc39f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
