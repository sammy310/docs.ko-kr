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
ms.openlocfilehash: 89fba6af9b76f729ca40d4ee63f525611bdf43a9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205642"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="d17b0-102">ICorDebugManagedCallback::CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="d17b0-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="d17b0-103">응용 프로그램 도메인이 생성 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d17b0-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d17b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="d17b0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d17b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d17b0-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d17b0-106">진행 응용 프로그램 도메인이 만들어진 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d17b0-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="d17b0-107">진행 만들어진 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d17b0-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d17b0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d17b0-108">Requirements</span></span>  
 <span data-ttu-id="d17b0-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d17b0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d17b0-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d17b0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d17b0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d17b0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d17b0-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d17b0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17b0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d17b0-113">See also</span></span>

- [<span data-ttu-id="d17b0-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d17b0-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
