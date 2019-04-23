---
title: ICoreClrDebugTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2972b87b2d0136f182f8e8223988953e1896f2bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183341"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="2de29-102">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2de29-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="2de29-103">참조 횟수를 제어, 프로세스, 열거 및 Macintosh Silverlight의 원격 대상에 연결 된 디버거를 사용 하 여 연결 된 메모리를 확보 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2de29-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de29-104">구문</span><span class="sxs-lookup"><span data-stu-id="2de29-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2de29-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2de29-105">Methods</span></span>  
  
|<span data-ttu-id="2de29-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2de29-106">Method</span></span>|<span data-ttu-id="2de29-107">설명</span><span class="sxs-lookup"><span data-stu-id="2de29-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2de29-108">ICoreClrDebugTarget::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="2de29-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="2de29-109">원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2de29-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="2de29-110">ICoreClrDebugTarget::EnumRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="2de29-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="2de29-111">원격 컴퓨터에서 지정된 된 프로세스에 공용 언어 런타임 (Clr)를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2de29-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="2de29-112">ICoreClrDebugTarget::FreeMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="2de29-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="2de29-113">이 클래스의 열거형 메서드에 의해 할당 된 메모리를 비웁니다.</span><span class="sxs-lookup"><span data-stu-id="2de29-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2de29-114">설명</span><span class="sxs-lookup"><span data-stu-id="2de29-114">Remarks</span></span>  
 <span data-ttu-id="2de29-115">현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상 디버깅에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2de29-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2de29-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2de29-116">Requirements</span></span>  
 <span data-ttu-id="2de29-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2de29-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2de29-118">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="2de29-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2de29-119">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2de29-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2de29-120">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2de29-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de29-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="2de29-121">See also</span></span>

- [<span data-ttu-id="2de29-122">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2de29-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="2de29-123">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2de29-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="2de29-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2de29-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
