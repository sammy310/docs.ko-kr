---
title: ICorDebugAppDomain::EnumerateBreakpoints 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996270"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="5c618-102">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="5c618-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="5c618-103">응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c618-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c618-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c618-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c618-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c618-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="5c618-106">[out] 응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자는 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c618-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c618-107">설명</span><span class="sxs-lookup"><span data-stu-id="5c618-107">Remarks</span></span>  
 <span data-ttu-id="5c618-108">열거자는 모든 유형의 함수 중단점 등 데이터 중단점, 중단점을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c618-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c618-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c618-109">Requirements</span></span>  
 <span data-ttu-id="5c618-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c618-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c618-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c618-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c618-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c618-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c618-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c618-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
