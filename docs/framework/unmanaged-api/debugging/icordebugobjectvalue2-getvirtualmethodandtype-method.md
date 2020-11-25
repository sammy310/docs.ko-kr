---
title: ICorDebugObjectValue2::GetVirtualMethodAndType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
ms.openlocfilehash: 2a74688b90fbce63c9107d9389ddfd7bf5cd717b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695181"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="e1e67-102">ICorDebugObjectValue2::GetVirtualMethodAndType 메서드</span><span class="sxs-lookup"><span data-stu-id="e1e67-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>

<span data-ttu-id="e1e67-103">이 메서드는 아직 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e1e67-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e67-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1e67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e1e67-105">설명</span><span class="sxs-lookup"><span data-stu-id="e1e67-105">Remarks</span></span>  

 <span data-ttu-id="e1e67-106">지정 된 멤버 참조에 대해 가장 많이 파생 된 메서드와 형식을 나타내는 "ICorDebugFunction" 및 "ICorDebugType" 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1e67-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e67-107">참조</span><span class="sxs-lookup"><span data-stu-id="e1e67-107">See also</span></span>
