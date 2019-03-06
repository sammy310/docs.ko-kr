---
title: ICorDebugEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1226f64df379b5c40304221e9e66eebcdb17b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479236"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="6d46d-102">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="6d46d-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="6d46d-103">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d46d-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d46d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d46d-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d46d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d46d-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="6d46d-106">[out] 주소에 대 한 포인터를 `ICorDebugEnum` 개체의 복사본 인 `ICorDebugEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6d46d-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d46d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d46d-107">Requirements</span></span>  
 <span data-ttu-id="6d46d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6d46d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d46d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d46d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d46d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d46d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d46d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d46d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
