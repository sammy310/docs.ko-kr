---
title: ICorDebugHandleValue::Dispose 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
ms.openlocfilehash: dc24afd8f78a900ea52539bf9dcb522287223c4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705633"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="13c8e-102">ICorDebugHandleValue::Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="13c8e-102">ICorDebugHandleValue::Dispose Method</span></span>

<span data-ttu-id="13c8e-103">인터페이스 포인터를 명시적으로 해제 하지 않고이 ICorDebugHandleValue 개체에서 참조 하는 핸들을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="13c8e-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c8e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13c8e-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="13c8e-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13c8e-105">Requirements</span></span>  

 <span data-ttu-id="13c8e-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13c8e-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c8e-107">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13c8e-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13c8e-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13c8e-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13c8e-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c8e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
