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
ms.openlocfilehash: 7293528bb119c23f6ef39405a82180252b336735
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687244"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="67f6a-102">ICorDebugEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="67f6a-102">ICorDebugEnum::GetCount Method</span></span>

<span data-ttu-id="67f6a-103">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="67f6a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67f6a-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="67f6a-106">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="67f6a-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f6a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67f6a-107">Requirements</span></span>  

 <span data-ttu-id="67f6a-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67f6a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f6a-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67f6a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67f6a-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67f6a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67f6a-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f6a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
