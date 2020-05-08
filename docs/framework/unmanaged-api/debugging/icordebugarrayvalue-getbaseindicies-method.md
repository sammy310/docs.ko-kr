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
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895064"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="f3be0-102">ICorDebugArrayValue::GetBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="f3be0-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="f3be0-103">배열에 있는 각 차원의 기본 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3be0-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3be0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3be0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3be0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3be0-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="f3be0-106">진행 이 `ICorDebugArrayValue` 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3be0-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="f3be0-107">이 값은 `indicies` 배열의 크기가 `ICorDebugArrayValue` 개체의 차원 수와 같으므로 배열의 크기 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3be0-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="f3be0-108">제한이 이 `ICorDebugArrayValue` 개체의 차원에 대 한 기본 인덱스 (즉, 시작 인덱스) 인 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f3be0-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3be0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3be0-109">Requirements</span></span>  
 <span data-ttu-id="f3be0-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3be0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3be0-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3be0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3be0-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3be0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3be0-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3be0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
