---
description: '자세히 알아보기: ICorDebugArrayValue:: GetElementAtPosition 메서드'
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
ms.openlocfilehash: ef8e4a39f5fe4088b1883803aee037c51f410241
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723035"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="f8108-103">ICorDebugArrayValue::GetElementAtPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="f8108-103">ICorDebugArrayValue::GetElementAtPosition Method</span></span>

<span data-ttu-id="f8108-104">배열을 0부터 시작 하는 1 차원 배열로 처리 하는 지정 된 위치에 있는 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8108-104">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8108-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8108-105">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8108-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8108-106">Parameters</span></span>  

 `nPosition`  
 <span data-ttu-id="f8108-107">진행 검색할 요소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f8108-107">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f8108-108">제한이 요소의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8108-108">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8108-109">설명</span><span class="sxs-lookup"><span data-stu-id="f8108-109">Remarks</span></span>  

 <span data-ttu-id="f8108-110">다중 차원 배열의 레이아웃은 배열 레이아웃의 c + + 스타일을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8108-110">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8108-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8108-111">Requirements</span></span>  

 <span data-ttu-id="f8108-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8108-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8108-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8108-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8108-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8108-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8108-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8108-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
