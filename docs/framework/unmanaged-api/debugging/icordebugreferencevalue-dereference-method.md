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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783021"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="48345-102">ICorDebugReferenceValue::Dereference 메서드</span><span class="sxs-lookup"><span data-stu-id="48345-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="48345-103">참조 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48345-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48345-104">구문</span><span class="sxs-lookup"><span data-stu-id="48345-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48345-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48345-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="48345-106">[out] 이 ICorDebugReferenceValue 개체가 가리키는 개체를 나타내는 ICorDebugValue의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48345-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48345-107">설명</span><span class="sxs-lookup"><span data-stu-id="48345-107">Remarks</span></span>  
 <span data-ttu-id="48345-108">`ICorDebugValue` 개체는 해당 참조가 아직 해제 되지 않은 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="48345-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48345-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48345-109">Requirements</span></span>  
 <span data-ttu-id="48345-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="48345-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48345-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48345-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48345-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48345-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48345-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48345-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
