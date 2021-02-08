---
description: '자세히 알아보기: ICorDebugManagedCallback:: ExitAppDomain 메서드'
title: ICorDebugManagedCallback::ExitAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
ms.openlocfilehash: a08f29c6c4c8196b968118433c31afb715935aec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803622"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="1dab1-103">ICorDebugManagedCallback::ExitAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="1dab1-103">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="1dab1-104">응용 프로그램 도메인이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1dab1-104">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dab1-105">구문</span><span class="sxs-lookup"><span data-stu-id="1dab1-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dab1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1dab1-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="1dab1-107">진행 지정 된 응용 프로그램 도메인을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1dab1-107">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1dab1-108">진행 종료 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1dab1-108">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dab1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1dab1-109">Requirements</span></span>  

 <span data-ttu-id="1dab1-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1dab1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dab1-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dab1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dab1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dab1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dab1-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dab1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dab1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dab1-114">See also</span></span>

- [<span data-ttu-id="1dab1-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1dab1-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
