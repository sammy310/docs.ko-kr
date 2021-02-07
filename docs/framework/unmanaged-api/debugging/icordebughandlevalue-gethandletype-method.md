---
description: '자세히 알아보기: ICorDebugHandleValue:: GetHandleType 메서드'
title: ICorDebugHandleValue::GetHandleType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: 708d60cd8116cf3f0fdc436a34d863380be2543d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660962"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="1df7b-103">ICorDebugHandleValue::GetHandleType 메서드</span><span class="sxs-lookup"><span data-stu-id="1df7b-103">ICorDebugHandleValue::GetHandleType Method</span></span>

<span data-ttu-id="1df7b-104">이 ICorDebugHandleValue 개체가 참조 하는 핸들의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1df7b-104">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df7b-105">구문</span><span class="sxs-lookup"><span data-stu-id="1df7b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1df7b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1df7b-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="1df7b-107">제한이 이 핸들의 유형을 나타내는 CorDebugHandleType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1df7b-107">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df7b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1df7b-108">Requirements</span></span>  

 <span data-ttu-id="1df7b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1df7b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df7b-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1df7b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1df7b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1df7b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1df7b-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
