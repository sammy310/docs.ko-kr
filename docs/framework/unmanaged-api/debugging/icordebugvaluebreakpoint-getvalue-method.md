---
description: '자세히 알아보기: ICorDebugValueBreakpoint:: GetValue 메서드'
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
ms.openlocfilehash: b690ea7a39ac70edd8e3e6be7682bae1e808555d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690173"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="99d68-103">ICorDebugValueBreakpoint::GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="99d68-103">ICorDebugValueBreakpoint::GetValue Method</span></span>

<span data-ttu-id="99d68-104">중단점이 설정 된 개체의 값을 나타내는 "ICorDebugValue" 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99d68-104">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d68-105">구문</span><span class="sxs-lookup"><span data-stu-id="99d68-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d68-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99d68-106">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="99d68-107">제한이 개체의 주소에 대 한 포인터 `ICorDebugValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="99d68-107">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d68-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99d68-108">Requirements</span></span>  

 <span data-ttu-id="99d68-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99d68-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d68-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99d68-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99d68-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99d68-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99d68-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d68-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d68-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99d68-113">See also</span></span>
