---
description: '자세히 알아보기: ICorDebugAppDomain:: EnumerateBreakpoints 메서드'
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
ms.openlocfilehash: 4bd9857b9c662bc76c7c9481f306b20e823e446f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772468"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="92ca3-103">ICorDebugAppDomain::EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="92ca3-103">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>

<span data-ttu-id="92ca3-104">응용 프로그램 도메인의 모든 활성 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92ca3-104">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ca3-105">구문</span><span class="sxs-lookup"><span data-stu-id="92ca3-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ca3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92ca3-106">Parameters</span></span>  

 `ppBreakpoints`  
 <span data-ttu-id="92ca3-107">제한이 응용 프로그램 도메인에 있는 모든 활성 중단점의 열거자 인 ICorDebugBreakpointEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="92ca3-107">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ca3-108">설명</span><span class="sxs-lookup"><span data-stu-id="92ca3-108">Remarks</span></span>  

 <span data-ttu-id="92ca3-109">열거자는 함수 중단점과 데이터 중단점을 포함 하 여 모든 형식의 중단점을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="92ca3-109">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ca3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92ca3-110">Requirements</span></span>  

 <span data-ttu-id="92ca3-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92ca3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ca3-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ca3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ca3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ca3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ca3-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ca3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
