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
ms.openlocfilehash: 8cb8699c103f48b42694449a2bb2bbd25c42d3c6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212732"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="a2eca-102">ICorDebugManagedCallback::LoadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="a2eca-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="a2eca-103">CLR (공용 언어 런타임) 어셈블리가 성공적으로 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a2eca-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2eca-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2eca-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2eca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2eca-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a2eca-106">진행 어셈블리가 로드 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2eca-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="a2eca-107">진행 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a2eca-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2eca-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2eca-108">Requirements</span></span>  
 <span data-ttu-id="a2eca-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2eca-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2eca-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2eca-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2eca-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2eca-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2eca-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2eca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2eca-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2eca-113">See also</span></span>

- [<span data-ttu-id="a2eca-114">UnloadAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="a2eca-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="a2eca-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2eca-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
