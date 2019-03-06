---
title: ICorDebugArrayValue::GetElement 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485306"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="b7b02-102">ICorDebugArrayValue::GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="b7b02-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="b7b02-103">지정 된 배열 요소의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b02-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7b02-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7b02-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="b7b02-106">[in] 이 차원 수가 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="b7b02-107">이 값은 또한의 크기를 `indices` 크기의 차원 수가 같음 이므로 배열는 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="b7b02-108">[in] 차원 내에서 위치를 지정 하는 각 인덱스 값의 배열을 `ICorDebugArrayValue` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="b7b02-109">이 값은 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b7b02-110">[out] 지정 된 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b02-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b02-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7b02-111">Requirements</span></span>  
 <span data-ttu-id="b7b02-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7b02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7b02-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7b02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7b02-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7b02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7b02-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7b02-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
