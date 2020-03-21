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
ms.openlocfilehash: 7c6d1905cdbd12b960014e687034ea9d163b68d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179034"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="d40b6-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="d40b6-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="d40b6-103">배열에서 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d40b6-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d40b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d40b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d40b6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d40b6-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="d40b6-106">【인】 이 `ICorDebugArrayValue` 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d40b6-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="d40b6-107">크기가 `ICorDebugArrayValue` 개체의 차원 `indicies` 수와 같기 때문에 이 값은 배열의 크기이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d40b6-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="d40b6-108">【아웃】 정수의 배열, 각 이 `ICorDebugArrayValue` 개체의 차원의 기본 인덱스 (즉, 시작 인덱스)입니다.</span><span class="sxs-lookup"><span data-stu-id="d40b6-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d40b6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d40b6-109">Requirements</span></span>  
 <span data-ttu-id="d40b6-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d40b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d40b6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d40b6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d40b6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d40b6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d40b6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d40b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
