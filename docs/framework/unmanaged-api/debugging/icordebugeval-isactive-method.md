---
description: '자세히 알아보기: ICorDebugEval:: IsActive 메서드'
title: ICorDebugEval::IsActive 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 2314814f8979f460063017ebdf46beb512417395
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694060"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="52d30-103">ICorDebugEval::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="52d30-103">ICorDebugEval::IsActive Method</span></span>

<span data-ttu-id="52d30-104">이 ICorDebugEval 개체가 현재 실행 중인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52d30-104">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d30-105">구문</span><span class="sxs-lookup"><span data-stu-id="52d30-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d30-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52d30-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="52d30-107">제한이 이 평가가 활성 상태 인지 여부를 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="52d30-107">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d30-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52d30-108">Requirements</span></span>  

 <span data-ttu-id="52d30-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52d30-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d30-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52d30-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52d30-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d30-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52d30-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d30-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
