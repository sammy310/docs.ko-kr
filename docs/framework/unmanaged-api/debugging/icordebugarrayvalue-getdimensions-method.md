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
ms.openlocfilehash: c5199794098e4d83588728eeb165aee5f81fe4c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088509"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="12363-102">ICorDebugArrayValue::GetDimensions 메서드</span><span class="sxs-lookup"><span data-stu-id="12363-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="12363-103">이 배열의 각 차원에 있는 요소의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12363-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12363-104">구문</span><span class="sxs-lookup"><span data-stu-id="12363-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12363-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12363-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="12363-106">진행 이 ICorDebugArrayValue 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="12363-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="12363-107">이 값은 `ICorDebugArrayValue` 개체의 크기와 같으므로 `dims` 배열의 크기 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="12363-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="12363-108">제한이 이 `ICorDebugArrayValue` 개체의 차원에 있는 요소의 수를 지정 하는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="12363-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12363-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12363-109">Requirements</span></span>  
 <span data-ttu-id="12363-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12363-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12363-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12363-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12363-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12363-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12363-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12363-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
