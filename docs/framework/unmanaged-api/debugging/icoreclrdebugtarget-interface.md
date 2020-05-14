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
ms.openlocfilehash: c44a12ef377d29e0b33b8be86aa1d8f0aa9d26bd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397152"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="fff16-102">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fff16-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="fff16-103">참조 횟수를 제어 하 고, 프로세스를 열거 하 고, 원격 Macintosh Silverlight 대상에 연결 된 디버거와 연결 된 메모리를 해제 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff16-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff16-104">구문</span><span class="sxs-lookup"><span data-stu-id="fff16-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="fff16-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fff16-105">Methods</span></span>  
  
|<span data-ttu-id="fff16-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fff16-106">Method</span></span>|<span data-ttu-id="fff16-107">Description</span><span class="sxs-lookup"><span data-stu-id="fff16-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fff16-108">ICoreClrDebugTarget::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="fff16-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="fff16-109">원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="fff16-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="fff16-110">ICoreClrDebugTarget::EnumRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="fff16-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="fff16-111">원격 컴퓨터에서 지정 된 프로세스의 Clr (공용 언어 런타임)을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff16-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="fff16-112">ICoreClrDebugTarget::FreeMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="fff16-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="fff16-113">이 클래스의 열거형 메서드에 의해 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fff16-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fff16-114">설명</span><span class="sxs-lookup"><span data-stu-id="fff16-114">Remarks</span></span>  
 <span data-ttu-id="fff16-115">현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상의 디버깅에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fff16-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fff16-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fff16-116">Requirements</span></span>  
 <span data-ttu-id="fff16-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fff16-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fff16-118">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="fff16-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fff16-119">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="fff16-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fff16-120">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fff16-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff16-121">참조</span><span class="sxs-lookup"><span data-stu-id="fff16-121">See also</span></span>

- [<span data-ttu-id="fff16-122">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fff16-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="fff16-123">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fff16-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="fff16-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fff16-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
