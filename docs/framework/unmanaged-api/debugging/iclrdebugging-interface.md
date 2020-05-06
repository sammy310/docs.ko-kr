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
ms.openlocfilehash: a3d4297e3b16dd1637e6293dbf7f04d4fbeda50f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860389"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="5eebe-102">ICLRDebugging 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eebe-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="5eebe-103">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5eebe-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5eebe-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5eebe-104">Methods</span></span>  
  
|<span data-ttu-id="5eebe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5eebe-105">Method</span></span>|<span data-ttu-id="5eebe-106">Description</span><span class="sxs-lookup"><span data-stu-id="5eebe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5eebe-107">OpenVirtualProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="5eebe-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="5eebe-108">프로세스에 로드 된 CLR (공용 언어 런타임) 모듈에 해당 하는 "ICorDebugProcess" 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5eebe-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="5eebe-109">CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="5eebe-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="5eebe-110">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) 인터페이스에서 제공 된 라이브러리가 아직 사용 중인지 또는 언로드될 수 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eebe-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eebe-111">설명</span><span class="sxs-lookup"><span data-stu-id="5eebe-111">Remarks</span></span>  
 <span data-ttu-id="5eebe-112">[Clrcreateinstance](../hosting/clrcreateinstance-function.md) 함수를 사용 하 여 `ICLRDebugging` 인터페이스의 인스턴스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eebe-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eebe-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5eebe-113">Requirements</span></span>  
 <span data-ttu-id="5eebe-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5eebe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eebe-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5eebe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5eebe-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5eebe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eebe-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eebe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eebe-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eebe-118">See also</span></span>

- [<span data-ttu-id="5eebe-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5eebe-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5eebe-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="5eebe-120">Debugging</span></span>](index.md)
