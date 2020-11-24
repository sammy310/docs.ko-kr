---
title: ICorDebugManagedCallback::LoadModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 698a5cb88884febc4dfb3b916c00df20c1a77819
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679652"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="0b03e-102">ICorDebugManagedCallback::LoadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="0b03e-102">ICorDebugManagedCallback::LoadModule Method</span></span>

<span data-ttu-id="0b03e-103">CLR (공용 언어 런타임) 모듈이 성공적으로 로드 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0b03e-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b03e-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b03e-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b03e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b03e-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="0b03e-106">진행 모듈이 로드 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0b03e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="0b03e-107">진행 CLR 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0b03e-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b03e-108">설명</span><span class="sxs-lookup"><span data-stu-id="0b03e-108">Remarks</span></span>  

 <span data-ttu-id="0b03e-109">`LoadModule`콜백은 모듈의 메타 데이터를 검사 하 고 JIT (just-in-time) 컴파일러 플래그를 설정 하거나 모듈에 대 한 클래스 로드 콜백을 사용 하거나 사용 하지 않도록 설정 하는 적절 한 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b03e-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b03e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b03e-110">Requirements</span></span>  

 <span data-ttu-id="0b03e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b03e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b03e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b03e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b03e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b03e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b03e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b03e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b03e-115">참조</span><span class="sxs-lookup"><span data-stu-id="0b03e-115">See also</span></span>

- [<span data-ttu-id="0b03e-116">UnloadModule 메서드</span><span class="sxs-lookup"><span data-stu-id="0b03e-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="0b03e-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b03e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
