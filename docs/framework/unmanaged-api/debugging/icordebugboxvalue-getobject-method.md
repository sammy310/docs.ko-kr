---
title: ICorDebugBoxValue::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c20eec52b0e4616af1b864bb58b6cbff44a720eb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490374"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="b809b-102">ICorDebugBoxValue::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="b809b-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="b809b-103">Boxed 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b809b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b809b-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b809b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b809b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="b809b-106">[out] Boxed 값을 나타내는 ICorDebugObjectValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b809b-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b809b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b809b-107">Requirements</span></span>  
 <span data-ttu-id="b809b-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b809b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b809b-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b809b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b809b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b809b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b809b-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b809b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
