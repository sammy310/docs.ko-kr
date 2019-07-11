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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcbe9a701b91a063e19fec5aae9cc2687b1f279f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766139"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="613ed-102">ICorDebugObjectValue2::GetVirtualMethodAndType 메서드</span><span class="sxs-lookup"><span data-stu-id="613ed-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="613ed-103">이 메서드는 아직 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="613ed-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="613ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="613ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="613ed-105">설명</span><span class="sxs-lookup"><span data-stu-id="613ed-105">Remarks</span></span>  
 <span data-ttu-id="613ed-106">가져옵니다 인터페이스 가장 많이 파생 된 메서드 및 지정 된 멤버 참조에 대 한 형식을 나타내는 "ICorDebugFunction" 및 "ICorDebugType" 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="613ed-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="613ed-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="613ed-107">See also</span></span>
