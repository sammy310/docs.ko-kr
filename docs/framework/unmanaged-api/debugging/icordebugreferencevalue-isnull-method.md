---
description: '자세히 알아보기: ICorDebugReferenceValue:: IsNull 메서드'
title: ICorDebugReferenceValue::IsNull 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: 9fffc869e20d1d3aa3a347ff2e026e6b55e6bd4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691031"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="df5cb-103">ICorDebugReferenceValue::IsNull 메서드</span><span class="sxs-lookup"><span data-stu-id="df5cb-103">ICorDebugReferenceValue::IsNull Method</span></span>

<span data-ttu-id="df5cb-104">이 ICorDebugReferenceValue가 null 값 인지 여부를 나타내는 값을 가져옵니다 .이 경우는 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df5cb-104">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df5cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="df5cb-105">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df5cb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df5cb-106">Parameters</span></span>  

 `pbNull`  
 <span data-ttu-id="df5cb-107">제한이 `true` 이 개체가 null 이면이 고, 그렇지 않으면 인 부울 값에 대 한 포인터이 `ICorDebugReferenceValue` 고, 그렇지 않으면입니다 `pbNull` `false` .</span><span class="sxs-lookup"><span data-stu-id="df5cb-107">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df5cb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df5cb-108">Requirements</span></span>  

 <span data-ttu-id="df5cb-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df5cb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df5cb-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df5cb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df5cb-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df5cb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df5cb-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df5cb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
