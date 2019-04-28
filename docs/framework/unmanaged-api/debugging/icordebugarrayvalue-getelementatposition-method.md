---
title: ICorDebugArrayValue::GetElementAtPosition 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76100116f2ca3a9b9a99477ca2352d5fa1335ab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645684"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="85bb4-102">ICorDebugArrayValue::GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="85bb4-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="85bb4-103">0부터 시작 하는 1 차원 배열로 간주 하 여 지정된 된 위치에서 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85bb4-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85bb4-104">구문</span><span class="sxs-lookup"><span data-stu-id="85bb4-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85bb4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85bb4-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="85bb4-106">[in] 검색할 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="85bb4-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="85bb4-107">[out] 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="85bb4-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85bb4-108">설명</span><span class="sxs-lookup"><span data-stu-id="85bb4-108">Remarks</span></span>  
 <span data-ttu-id="85bb4-109">다차원 배열의 레이아웃이 C++ 의 배열 레이아웃 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="85bb4-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85bb4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85bb4-110">Requirements</span></span>  
 <span data-ttu-id="85bb4-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85bb4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85bb4-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85bb4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85bb4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85bb4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85bb4-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85bb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
