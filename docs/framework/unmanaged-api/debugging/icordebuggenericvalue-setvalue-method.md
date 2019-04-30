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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae64fcccb49123f34cca2622a972a89bf700904f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995545"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="f3d1f-102">ICorDebugGenericValue::SetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="f3d1f-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="f3d1f-103">지정된 된 버퍼에서 새 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d1f-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3d1f-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3d1f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3d1f-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="f3d1f-106">[in] 값을 복사해 올 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d1f-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d1f-107">설명</span><span class="sxs-lookup"><span data-stu-id="f3d1f-107">Remarks</span></span>  
 <span data-ttu-id="f3d1f-108">참조 형식의 경우 값은 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d1f-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d1f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3d1f-109">Requirements</span></span>  
 <span data-ttu-id="f3d1f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3d1f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d1f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3d1f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3d1f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3d1f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3d1f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d1f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
