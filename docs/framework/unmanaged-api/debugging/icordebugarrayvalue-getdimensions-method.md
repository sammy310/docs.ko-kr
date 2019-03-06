---
title: ICorDebugArrayValue::GetDimensions 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52075f33d594787c516f84b65b3319991380907
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500378"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="32edc-102">ICorDebugArrayValue::GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="32edc-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="32edc-103">이 배열의 각 차원에서 요소의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32edc-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32edc-104">구문</span><span class="sxs-lookup"><span data-stu-id="32edc-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32edc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32edc-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="32edc-106">[in] 이 ICorDebugArrayValue 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="32edc-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="32edc-107">이 값은 또한의 크기를 `dims` 크기의 차원 수가 같음 이므로 배열는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="32edc-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="32edc-108">[out] 이 차원에서 요소의 수를 지정 각각 정수의 배열을 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="32edc-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32edc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32edc-109">Requirements</span></span>  
 <span data-ttu-id="32edc-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="32edc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32edc-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32edc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32edc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32edc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32edc-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32edc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
