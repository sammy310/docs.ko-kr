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
ms.openlocfilehash: a9d1faf5a834cb5d9be19f995aaa3eee1202171b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727447"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="a78bc-102">ICorDebugArrayValue::HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="a78bc-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="a78bc-103">이 배열의 모든 차원에 0이 아닌 기본 인덱스가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a78bc-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="a78bc-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a78bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a78bc-105">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="a78bc-106">제한이 `true` 이 개체의 차원 중 하나 이상에 `ICorDebugArrayValue` 0이 아닌 기본 인덱스가 있으면이 고, 그렇지 않으면 부울 값에 대 한 포인터입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="a78bc-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a78bc-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a78bc-107">Requirements</span></span>  

 <span data-ttu-id="a78bc-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a78bc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a78bc-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a78bc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a78bc-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a78bc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a78bc-111">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a78bc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
