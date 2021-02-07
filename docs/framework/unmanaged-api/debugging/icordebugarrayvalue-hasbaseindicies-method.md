---
description: '자세히 알아보기: ICorDebugArrayValue:: HasBaseIndicies 메서드'
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
ms.openlocfilehash: b251653004801ff2d312dfb34749c413774ddf40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722960"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="50f4b-103">ICorDebugArrayValue::HasBaseIndicies 메서드</span><span class="sxs-lookup"><span data-stu-id="50f4b-103">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="50f4b-104">이 배열의 모든 차원에 0이 아닌 기본 인덱스가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50f4b-104">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f4b-105">구문</span><span class="sxs-lookup"><span data-stu-id="50f4b-105">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50f4b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50f4b-106">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="50f4b-107">제한이 `true` 이 개체의 차원 중 하나 이상에 `ICorDebugArrayValue` 0이 아닌 기본 인덱스가 있으면이 고, 그렇지 않으면 부울 값에 대 한 포인터입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="50f4b-107">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f4b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50f4b-108">Requirements</span></span>  

 <span data-ttu-id="50f4b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50f4b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f4b-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50f4b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50f4b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50f4b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50f4b-112">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f4b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
