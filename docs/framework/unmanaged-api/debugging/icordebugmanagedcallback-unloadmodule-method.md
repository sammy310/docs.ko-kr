---
title: ICorDebugManagedCallback::UnloadModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 88ef9fd5a0aac19954a247d0215fe698ebe30d40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788328"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="00917-102">ICorDebugManagedCallback::UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="00917-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="00917-103">DLL (공용 언어 런타임 모듈)이 언로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="00917-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00917-104">구문</span><span class="sxs-lookup"><span data-stu-id="00917-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00917-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00917-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="00917-106">진행 모듈이 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="00917-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="00917-107">진행 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="00917-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00917-108">주의</span><span class="sxs-lookup"><span data-stu-id="00917-108">Remarks</span></span>  
 <span data-ttu-id="00917-109">이 호출 후에는 모듈을 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00917-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00917-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00917-110">Requirements</span></span>  
 <span data-ttu-id="00917-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00917-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00917-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00917-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00917-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00917-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00917-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00917-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00917-115">참조</span><span class="sxs-lookup"><span data-stu-id="00917-115">See also</span></span>

- [<span data-ttu-id="00917-116">LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="00917-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="00917-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00917-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
