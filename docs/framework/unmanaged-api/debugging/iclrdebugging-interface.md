---
title: ICLRDebugging 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793635"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="f33a1-102">ICLRDebugging 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f33a1-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="f33a1-103">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f33a1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f33a1-104">Methods</span></span>  
  
|<span data-ttu-id="f33a1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f33a1-105">Method</span></span>|<span data-ttu-id="f33a1-106">설명</span><span class="sxs-lookup"><span data-stu-id="f33a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f33a1-107">OpenVirtualProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="f33a1-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="f33a1-108">프로세스에 로드 된 CLR (공용 언어 런타임) 모듈에 해당 하는 "ICorDebugProcess" 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="f33a1-109">CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="f33a1-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="f33a1-110">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) 인터페이스에서 제공 된 라이브러리가 아직 사용 중인지 또는 언로드될 수 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f33a1-111">주의</span><span class="sxs-lookup"><span data-stu-id="f33a1-111">Remarks</span></span>  
 <span data-ttu-id="f33a1-112">[Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수를 사용 하 여 `ICLRDebugging` 인터페이스의 인스턴스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f33a1-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f33a1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f33a1-113">Requirements</span></span>  
 <span data-ttu-id="f33a1-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f33a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f33a1-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f33a1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f33a1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f33a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f33a1-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f33a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f33a1-118">참조</span><span class="sxs-lookup"><span data-stu-id="f33a1-118">See also</span></span>

- [<span data-ttu-id="f33a1-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f33a1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f33a1-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="f33a1-120">Debugging</span></span>](index.md)
