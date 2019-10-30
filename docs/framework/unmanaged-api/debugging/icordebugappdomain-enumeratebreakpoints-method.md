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
ms.openlocfilehash: 3611684a17d51fc4fdba31dd4049540039b43e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110513"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="46122-102">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="46122-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="46122-103">응용 프로그램 도메인의 모든 활성 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46122-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46122-104">구문</span><span class="sxs-lookup"><span data-stu-id="46122-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46122-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46122-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="46122-106">제한이 응용 프로그램 도메인에 있는 모든 활성 중단점의 열거자 인 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46122-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46122-107">주의</span><span class="sxs-lookup"><span data-stu-id="46122-107">Remarks</span></span>  
 <span data-ttu-id="46122-108">열거자는 함수 중단점과 데이터 중단점을 포함 하 여 모든 형식의 중단점을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="46122-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46122-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46122-109">Requirements</span></span>  
 <span data-ttu-id="46122-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46122-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46122-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46122-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46122-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46122-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46122-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46122-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
