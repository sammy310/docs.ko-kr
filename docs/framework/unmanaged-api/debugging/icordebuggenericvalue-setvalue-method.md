---
title: ICorDebugGenericValue::SetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
ms.openlocfilehash: 493793c45e7d13511e4c36fe76e472a856b50d72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705750"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="b3402-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="b3402-102">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="b3402-103">지정 된 버퍼에서 새 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3402-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3402-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3402-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3402-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3402-105">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="b3402-106">진행 값을 복사할 원본 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3402-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3402-107">설명</span><span class="sxs-lookup"><span data-stu-id="b3402-107">Remarks</span></span>  

 <span data-ttu-id="b3402-108">참조 형식의 경우 값은 콘텐츠가 아닌 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="b3402-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3402-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3402-109">Requirements</span></span>  

 <span data-ttu-id="b3402-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3402-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3402-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3402-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3402-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3402-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3402-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3402-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
