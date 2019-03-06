---
title: ICorDebugReferenceValue::Dereference 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b436fa14322d444a6c8b515ba8e50698eecb95ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487020"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="ab8f6-102">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="ab8f6-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="ab8f6-103">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab8f6-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab8f6-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab8f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab8f6-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="ab8f6-106">[out] 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab8f6-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab8f6-107">설명</span><span class="sxs-lookup"><span data-stu-id="ab8f6-107">Remarks</span></span>  
 <span data-ttu-id="ab8f6-108">`ICorDebugValue` 개체는 해당 참조가 아직 해제 되지 않은 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8f6-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab8f6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab8f6-109">Requirements</span></span>  
 <span data-ttu-id="ab8f6-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab8f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab8f6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab8f6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab8f6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab8f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab8f6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab8f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
