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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afd8bd76f8d738c9eaa3a8e3d490e175e408b92b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204304"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="fed5c-102">ICorDebugManagedCallback::CreateAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="fed5c-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="fed5c-103">응용 프로그램 도메인이 만들어졌는지 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fed5c-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="fed5c-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed5c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fed5c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="fed5c-106">[in] 응용 프로그램 도메인 생성 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fed5c-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fed5c-107">[in] 작성 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fed5c-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed5c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fed5c-108">Requirements</span></span>  
 <span data-ttu-id="fed5c-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fed5c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed5c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed5c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed5c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed5c-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fed5c-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="fed5c-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fed5c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="fed5c-113">See also</span></span>

- [<span data-ttu-id="fed5c-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fed5c-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
