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
ms.openlocfilehash: 9f0fda803ba3a1ce35017d85e84b3bf6f567eda0
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976371"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="439ff-102">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="439ff-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="439ff-103">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="439ff-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="439ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="439ff-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="439ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="439ff-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="439ff-106">제한이 이 `ICorDebugEnum` `ICorDebugEnum` 개체의 복사본 인 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="439ff-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="439ff-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="439ff-107">Requirements</span></span>  
 <span data-ttu-id="439ff-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="439ff-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="439ff-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="439ff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="439ff-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="439ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="439ff-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="439ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
