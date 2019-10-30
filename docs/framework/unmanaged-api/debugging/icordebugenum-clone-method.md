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
ms.openlocfilehash: 2ec769c343ad055132c6d84e64600fc459357a85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124702"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="10ac7-102">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="10ac7-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="10ac7-103">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10ac7-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ac7-104">구문</span><span class="sxs-lookup"><span data-stu-id="10ac7-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10ac7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10ac7-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="10ac7-106">제한이 이 `ICorDebugEnum` 개체의 복사본 인 `ICorDebugEnum` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="10ac7-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ac7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10ac7-107">Requirements</span></span>  
 <span data-ttu-id="10ac7-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10ac7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ac7-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10ac7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10ac7-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10ac7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10ac7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ac7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
