---
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
ms.openlocfilehash: d133cacb611a1c7bd03d7653f46c2e5fb1acc043
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723352"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="1ef34-102">ICorDebugAppDomain::Attach 메서드</span><span class="sxs-lookup"><span data-stu-id="1ef34-102">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="1ef34-103">응용 프로그램 도메인에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef34-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef34-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ef34-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1ef34-105">설명</span><span class="sxs-lookup"><span data-stu-id="1ef34-105">Remarks</span></span>  

 <span data-ttu-id="1ef34-106">이벤트를 수신 하 고 응용 프로그램 도메인의 디버깅을 사용 하도록 설정 하려면 응용 프로그램 도메인에 디버거를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ef34-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef34-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ef34-107">Requirements</span></span>  

 <span data-ttu-id="1ef34-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ef34-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef34-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ef34-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ef34-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ef34-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ef34-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef34-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
