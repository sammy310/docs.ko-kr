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
ms.openlocfilehash: df151e9fc89214d0851ebe60c7ebdb87224f880c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719088"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="bfc65-102">ICorDebugBoxValue::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="bfc65-102">ICorDebugBoxValue::GetObject Method</span></span>

<span data-ttu-id="bfc65-103">Boxed 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfc65-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfc65-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfc65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfc65-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfc65-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="bfc65-106">제한이 Boxed 값을 나타내는 ICorDebugObjectValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc65-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfc65-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfc65-107">Requirements</span></span>  

 <span data-ttu-id="bfc65-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfc65-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfc65-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfc65-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfc65-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfc65-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfc65-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfc65-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
