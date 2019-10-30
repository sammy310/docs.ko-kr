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
ms.openlocfilehash: 3d45caae56403d77776f1a8adbb5fb9c368ff105
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088486"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="bd346-102">ICorDebugArrayValue::GetElement 메서드</span><span class="sxs-lookup"><span data-stu-id="bd346-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="bd346-103">지정 된 배열 요소의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd346-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd346-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd346-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd346-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="bd346-106">진행 이 `ICorDebugArrayValue` 개체의 차원 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="bd346-107">이 값은 `ICorDebugArrayValue` 개체의 크기와 같으므로 `indices` 배열의 크기 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="bd346-108">진행 각각 `ICorDebugArrayValue` 개체의 차원 내에서 위치를 지정 하는 인덱스 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="bd346-109">이 값은 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bd346-110">제한이 지정 된 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd346-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd346-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd346-111">Requirements</span></span>  
 <span data-ttu-id="bd346-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd346-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd346-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd346-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd346-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd346-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd346-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd346-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
