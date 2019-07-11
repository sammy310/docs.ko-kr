---
title: ICorDebugEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f823f660efee2d53bc1f6fa50d8878f496417379
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752283"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="b51e1-102">ICorDebugEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="b51e1-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="b51e1-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b51e1-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b51e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="b51e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b51e1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b51e1-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="b51e1-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e1-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b51e1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b51e1-107">Requirements</span></span>  
 <span data-ttu-id="b51e1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b51e1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b51e1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b51e1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b51e1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b51e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b51e1-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b51e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
