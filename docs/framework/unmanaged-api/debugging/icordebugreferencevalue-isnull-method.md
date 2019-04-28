---
title: ICorDebugReferenceValue::IsNull 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 972df4613255dc1b71801e02d387a735dfc632c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782937"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="0f5f4-102">ICorDebugReferenceValue::IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="0f5f4-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="0f5f4-103">이 ICorDebugReferenceValue 경우 null 값을 인지 여부를 나타내는 값을 가져옵니다는 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5f4-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f5f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f5f4-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f5f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f5f4-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="0f5f4-106">[out] 부울 값에 대 한 포인터 `true` 이 `ICorDebugReferenceValue` 고, 그렇지 않으면 null 개체가 `pbNull` 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5f4-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f5f4-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f5f4-107">Requirements</span></span>  
 <span data-ttu-id="0f5f4-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f5f4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f5f4-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f5f4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f5f4-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f5f4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f5f4-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f5f4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
