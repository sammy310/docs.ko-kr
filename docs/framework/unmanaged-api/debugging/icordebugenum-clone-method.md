---
description: '자세히 알아보기: ICorDebugEnum:: Clone 메서드'
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
ms.openlocfilehash: 18219757980870dcf9663477d195068a76814de1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694580"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="5f18d-103">ICorDebugEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="5f18d-103">ICorDebugEnum::Clone Method</span></span>

<span data-ttu-id="5f18d-104">이 ICorDebugEnum 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f18d-104">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f18d-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f18d-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f18d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f18d-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5f18d-107">제한이 `ICorDebugEnum` 이 개체의 복사본 인 개체의 주소에 대 한 포인터입니다 `ICorDebugEnum` .</span><span class="sxs-lookup"><span data-stu-id="5f18d-107">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f18d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f18d-108">Requirements</span></span>  

 <span data-ttu-id="5f18d-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f18d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f18d-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f18d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f18d-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f18d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f18d-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f18d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
