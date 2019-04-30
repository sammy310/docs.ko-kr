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
ms.openlocfilehash: b4af328c537fbc3b64eb1a2ac3df3a4e4224789e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996023"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="28249-102">ICorDebugEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="28249-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="28249-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="28249-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28249-104">구문</span><span class="sxs-lookup"><span data-stu-id="28249-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28249-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28249-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="28249-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28249-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28249-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28249-107">Requirements</span></span>  
 <span data-ttu-id="28249-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28249-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28249-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28249-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28249-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28249-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28249-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28249-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
