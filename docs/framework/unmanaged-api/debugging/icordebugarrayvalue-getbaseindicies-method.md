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
ms.openlocfilehash: e103401b85626e53db53e1894c22b161774e5163
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088685"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="cf5ea-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="cf5ea-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="cf5ea-103">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ea-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf5ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf5ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf5ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf5ea-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="cf5ea-106">진행 이 `ICorDebugArrayValue` 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ea-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="cf5ea-107">이 값은 `ICorDebugArrayValue` 개체의 크기와 같으므로 `indicies` 배열의 크기 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ea-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="cf5ea-108">제한이 이 `ICorDebugArrayValue` 개체의 차원에 대 한 기본 인덱스 (즉, 시작 인덱스) 인 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ea-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf5ea-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf5ea-109">Requirements</span></span>  
 <span data-ttu-id="cf5ea-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf5ea-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf5ea-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf5ea-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf5ea-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf5ea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf5ea-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf5ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
