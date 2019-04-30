---
title: ICorDebugManagedCallback::LoadAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5760287e01257e3f0fc99a18ba20f2f2a1b2b3af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988158"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="f7a38-102">ICorDebugManagedCallback::LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="f7a38-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="f7a38-103">공용 언어 런타임 (CLR) 어셈블리를 성공적으로 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f7a38-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a38-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7a38-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7a38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7a38-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f7a38-106">[in] ICorDebugAppDomain 개체는 어셈블리 로드 된 응용 프로그램 도메인을 나타내는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a38-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="f7a38-107">[in] 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a38-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a38-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7a38-108">Requirements</span></span>  
 <span data-ttu-id="f7a38-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a38-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a38-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7a38-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7a38-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7a38-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7a38-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a38-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a38-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7a38-113">See also</span></span>

- [<span data-ttu-id="f7a38-114">UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="f7a38-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="f7a38-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7a38-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
