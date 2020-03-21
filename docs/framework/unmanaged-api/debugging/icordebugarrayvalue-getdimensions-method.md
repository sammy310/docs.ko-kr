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
ms.openlocfilehash: 35e043c56977bf644efe1dd9cee1409f50cc877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179023"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="b2825-102">ICorDebugArrayValue::GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="b2825-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="b2825-103">이 배열의 각 차원에 있는 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2825-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2825-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2825-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2825-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2825-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="b2825-106">【인】 이 ICorDebugArrayValue 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2825-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="b2825-107">크기가 `ICorDebugArrayValue` 개체의 차원 `dims` 수와 같기 때문에 이 값은 배열의 크기이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2825-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="b2825-108">【아웃】 이 `ICorDebugArrayValue` 개체의 차원에 있는 요소 수를 지정하는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b2825-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2825-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2825-109">Requirements</span></span>  
 <span data-ttu-id="b2825-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2825-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2825-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2825-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2825-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2825-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2825-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2825-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
