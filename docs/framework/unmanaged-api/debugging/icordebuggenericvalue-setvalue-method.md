---
description: '자세히 알아보기: ICorDebugGenericValue:: SetValue 메서드'
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
ms.openlocfilehash: e284d9987c8428fadedde0024fd3c65a0d8fe7a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791480"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="07ca9-103">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="07ca9-103">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="07ca9-104">지정 된 버퍼에서 새 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="07ca9-104">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ca9-105">구문</span><span class="sxs-lookup"><span data-stu-id="07ca9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07ca9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07ca9-106">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="07ca9-107">진행 값을 복사할 원본 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07ca9-107">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07ca9-108">설명</span><span class="sxs-lookup"><span data-stu-id="07ca9-108">Remarks</span></span>  

 <span data-ttu-id="07ca9-109">참조 형식의 경우 값은 콘텐츠가 아닌 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="07ca9-109">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ca9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07ca9-110">Requirements</span></span>  

 <span data-ttu-id="07ca9-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07ca9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ca9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07ca9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07ca9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07ca9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07ca9-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ca9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
