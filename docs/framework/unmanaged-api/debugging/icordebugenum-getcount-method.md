---
description: '자세히 알아보기: ICorDebugEnum:: GetCount 메서드'
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
ms.openlocfilehash: 38fa85958ea0c6945a5575d12700701ed355891d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694559"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="02c07-103">ICorDebugEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="02c07-103">ICorDebugEnum::GetCount Method</span></span>

<span data-ttu-id="02c07-104">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c07-104">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c07-105">구문</span><span class="sxs-lookup"><span data-stu-id="02c07-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02c07-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02c07-106">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="02c07-107">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02c07-107">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02c07-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02c07-108">Requirements</span></span>  

 <span data-ttu-id="02c07-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02c07-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c07-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02c07-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02c07-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02c07-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02c07-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c07-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
