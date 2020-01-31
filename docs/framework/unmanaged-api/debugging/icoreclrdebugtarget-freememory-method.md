---
title: ICoreClrDebugTarget::FreeMemory 메서드
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: cfa313d286d0decad82f51bcedc582470549c8e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790781"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="9ff29-102">ICoreClrDebugTarget::FreeMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="9ff29-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="9ff29-103">[ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 및 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff29-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff29-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ff29-104">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ff29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ff29-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="9ff29-106">진행 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 또는 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 반환 된 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff29-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff29-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ff29-107">Requirements</span></span>  
 <span data-ttu-id="9ff29-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ff29-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff29-109">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="9ff29-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9ff29-110">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="9ff29-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9ff29-111">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9ff29-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff29-112">참조</span><span class="sxs-lookup"><span data-stu-id="9ff29-112">See also</span></span>

- [<span data-ttu-id="9ff29-113">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ff29-113">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
