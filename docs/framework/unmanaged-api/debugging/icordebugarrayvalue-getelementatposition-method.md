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
ms.openlocfilehash: 5644c20ec5df2606c7258131573691997f424e50
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895021"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="4a507-102">ICorDebugArrayValue::GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="4a507-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="4a507-103">배열을 0부터 시작 하는 1 차원 배열로 처리 하는 지정 된 위치에 있는 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a507-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a507-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a507-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a507-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a507-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="4a507-106">진행 검색할 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4a507-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4a507-107">제한이 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a507-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a507-108">설명</span><span class="sxs-lookup"><span data-stu-id="4a507-108">Remarks</span></span>  
 <span data-ttu-id="4a507-109">다중 차원 배열의 레이아웃은 배열 레이아웃의 c + + 스타일을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4a507-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a507-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a507-110">Requirements</span></span>  
 <span data-ttu-id="4a507-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a507-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a507-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a507-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a507-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a507-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a507-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a507-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
