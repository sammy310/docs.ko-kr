---
title: ICorDebugValueBreakpoint::GetValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
ms.openlocfilehash: 5924a3914c7fe04413b4a6744bce263b56165d78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140220"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="ba26e-102">ICorDebugValueBreakpoint::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="ba26e-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="ba26e-103">중단점이 설정 된 개체의 값을 나타내는 "ICorDebugValue" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba26e-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba26e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba26e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba26e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba26e-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="ba26e-106">제한이 `ICorDebugValue` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba26e-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba26e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba26e-107">Requirements</span></span>  
 <span data-ttu-id="ba26e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba26e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba26e-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba26e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba26e-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba26e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba26e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba26e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba26e-112">참조</span><span class="sxs-lookup"><span data-stu-id="ba26e-112">See also</span></span>
