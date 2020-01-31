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
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788350"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="4cf39-102">ICorDebugManagedCallback::UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="4cf39-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="4cf39-103">공용 언어 런타임 어셈블리가 언로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4cf39-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf39-104">구문</span><span class="sxs-lookup"><span data-stu-id="4cf39-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cf39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cf39-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4cf39-106">진행 어셈블리를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf39-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="4cf39-107">진행 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf39-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf39-108">주의</span><span class="sxs-lookup"><span data-stu-id="4cf39-108">Remarks</span></span>  
 <span data-ttu-id="4cf39-109">이 콜백 후에는 어셈블리를 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cf39-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf39-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cf39-110">Requirements</span></span>  
 <span data-ttu-id="4cf39-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cf39-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf39-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cf39-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cf39-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cf39-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cf39-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf39-115">참조</span><span class="sxs-lookup"><span data-stu-id="4cf39-115">See also</span></span>

- [<span data-ttu-id="4cf39-116">LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="4cf39-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="4cf39-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4cf39-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
