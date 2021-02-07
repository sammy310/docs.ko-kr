---
description: '자세히 알아보기: ICorDebugAppDomain:: Attach 메서드'
title: ICorDebugAppDomain::Attach 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 94448937a735b30d0403a207992dae29920a93bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754279"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="a0cf6-103">ICorDebugAppDomain::Attach 메서드</span><span class="sxs-lookup"><span data-stu-id="a0cf6-103">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="a0cf6-104">응용 프로그램 도메인에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cf6-104">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0cf6-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0cf6-105">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a0cf6-106">설명</span><span class="sxs-lookup"><span data-stu-id="a0cf6-106">Remarks</span></span>  

 <span data-ttu-id="a0cf6-107">이벤트를 수신 하 고 응용 프로그램 도메인의 디버깅을 사용 하도록 설정 하려면 응용 프로그램 도메인에 디버거를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cf6-107">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0cf6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0cf6-108">Requirements</span></span>  

 <span data-ttu-id="a0cf6-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0cf6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0cf6-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0cf6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0cf6-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0cf6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0cf6-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0cf6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
