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
ms.openlocfilehash: 20c8a1987e48a88a3b8c92cf9f36fb58166cda9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715981"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="6f000-102">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="6f000-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>

<span data-ttu-id="6f000-103">응용 프로그램 도메인의 모든 활성 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f000-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f000-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f000-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f000-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f000-105">Parameters</span></span>  

 `ppBreakpoints`  
 <span data-ttu-id="6f000-106">제한이 응용 프로그램 도메인에 있는 모든 활성 중단점의 열거자 인 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f000-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f000-107">설명</span><span class="sxs-lookup"><span data-stu-id="6f000-107">Remarks</span></span>  

 <span data-ttu-id="6f000-108">열거자는 함수 중단점과 데이터 중단점을 포함 하 여 모든 형식의 중단점을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f000-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f000-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f000-109">Requirements</span></span>  

 <span data-ttu-id="6f000-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f000-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f000-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f000-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f000-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f000-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f000-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f000-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
