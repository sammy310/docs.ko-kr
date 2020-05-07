---
title: ICorDebugBoxValue::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
ms.openlocfilehash: 401f052b881c1a0cfa065ba60c93aca1706f34f4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894777"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="7bf70-102">ICorDebugBoxValue::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="7bf70-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="7bf70-103">Boxed 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bf70-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf70-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bf70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bf70-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="7bf70-106">제한이 Boxed 값을 나타내는 ICorDebugObjectValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf70-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf70-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bf70-107">Requirements</span></span>  
 <span data-ttu-id="7bf70-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf70-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf70-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bf70-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bf70-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bf70-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bf70-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf70-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
