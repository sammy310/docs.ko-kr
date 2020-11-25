---
title: ICorDebugArrayValue::GetElementType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: 1deadef7517772460adc96cd0dd630d85cb21c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698169"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="a3d08-102">ICorDebugArrayValue::GetElementType 메서드</span><span class="sxs-lookup"><span data-stu-id="a3d08-102">ICorDebugArrayValue::GetElementType Method</span></span>

<span data-ttu-id="a3d08-103">배열에 있는 요소의 단순 형식을 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3d08-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d08-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3d08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d08-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3d08-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="a3d08-106">제한이 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3d08-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d08-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3d08-107">Requirements</span></span>  

 <span data-ttu-id="a3d08-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3d08-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d08-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3d08-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3d08-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3d08-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3d08-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d08-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
