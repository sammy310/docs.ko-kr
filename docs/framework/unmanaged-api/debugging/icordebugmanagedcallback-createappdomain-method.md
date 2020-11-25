---
title: ICorDebugManagedCallback::CreateAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
ms.openlocfilehash: 5f831f0f42231f594e170567535af75216e68c45
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721311"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="7d8aa-102">ICorDebugManagedCallback::CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="7d8aa-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>

<span data-ttu-id="7d8aa-103">응용 프로그램 도메인이 생성 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7d8aa-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d8aa-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d8aa-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="7d8aa-106">진행 응용 프로그램 도메인이 만들어진 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8aa-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="7d8aa-107">진행 만들어진 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8aa-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8aa-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d8aa-108">Requirements</span></span>  

 <span data-ttu-id="7d8aa-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d8aa-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8aa-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d8aa-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d8aa-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d8aa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d8aa-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8aa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8aa-113">참조</span><span class="sxs-lookup"><span data-stu-id="7d8aa-113">See also</span></span>

- [<span data-ttu-id="7d8aa-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d8aa-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
