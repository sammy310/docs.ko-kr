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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24a1434f737e8281a0c68dd09d2e17b34371694
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471656"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="48bfd-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="48bfd-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="48bfd-103">배열의 각 차원에 대 한 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48bfd-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48bfd-104">구문</span><span class="sxs-lookup"><span data-stu-id="48bfd-104">Syntax</span></span>  
  
```  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48bfd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48bfd-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="48bfd-106">[in] 이 차원 수가 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfd-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="48bfd-107">이 값은 또한의 크기를 `indicies` 크기의 차원 수가 같음 이므로 배열는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfd-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="48bfd-108">[out] 이 차원에 대 한 기본 인덱스 (즉, 시작 인덱스)은 각각 정수의 배열을 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48bfd-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48bfd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48bfd-109">Requirements</span></span>  
 <span data-ttu-id="48bfd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="48bfd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48bfd-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48bfd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48bfd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48bfd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48bfd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48bfd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
