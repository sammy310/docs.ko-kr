---
title: ICorDebugArrayValue::HasBaseIndicies 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49f5ed8b24d81ba8f32a9fe0ad7488693718bde9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645671"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="42aad-102">ICorDebugArrayValue::HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="42aad-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="42aad-103">이 배열의 모든 차원 0이 아닌 기본 인덱스 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="42aad-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42aad-104">구문</span><span class="sxs-lookup"><span data-stu-id="42aad-104">Syntax</span></span>  
  
```  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42aad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42aad-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="42aad-106">[out] 부울 값에 대 한 포인터 `true` 경우이 하나 이상의 차원을 `ICorDebugArrayValue` 개체의 0이 아닌 기본 인덱스가 고, 그렇지 않으면 부울 값을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="42aad-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42aad-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42aad-107">Requirements</span></span>  
 <span data-ttu-id="42aad-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42aad-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42aad-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42aad-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42aad-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42aad-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42aad-111">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42aad-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
