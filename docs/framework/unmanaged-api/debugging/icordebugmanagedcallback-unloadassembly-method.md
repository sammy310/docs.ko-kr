---
title: ICorDebugManagedCallback::UnloadAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 4ae4856eca2c1441ea53df0d9ed3648700b39b24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130648"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="178ac-102">ICorDebugManagedCallback::UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="178ac-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="178ac-103">공용 언어 런타임 어셈블리가 언로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="178ac-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="178ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="178ac-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="178ac-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="178ac-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="178ac-106">진행 어셈블리를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="178ac-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="178ac-107">진행 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="178ac-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="178ac-108">주의</span><span class="sxs-lookup"><span data-stu-id="178ac-108">Remarks</span></span>  
 <span data-ttu-id="178ac-109">이 콜백 후에는 어셈블리를 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="178ac-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="178ac-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="178ac-110">Requirements</span></span>  
 <span data-ttu-id="178ac-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="178ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="178ac-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="178ac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="178ac-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="178ac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="178ac-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="178ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178ac-115">참조</span><span class="sxs-lookup"><span data-stu-id="178ac-115">See also</span></span>

- [<span data-ttu-id="178ac-116">LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="178ac-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="178ac-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="178ac-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
