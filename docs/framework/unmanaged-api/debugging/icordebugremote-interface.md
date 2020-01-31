---
title: ICorDebugRemote 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
ms.openlocfilehash: 0cc79c0a93fa4f05b8c793a8b7fb0b9b3f031b1a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791959"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="12b23-102">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12b23-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="12b23-103">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12b23-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b23-104">구문</span><span class="sxs-lookup"><span data-stu-id="12b23-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="12b23-105">메서드</span><span class="sxs-lookup"><span data-stu-id="12b23-105">Methods</span></span>  
  
|<span data-ttu-id="12b23-106">메서드</span><span class="sxs-lookup"><span data-stu-id="12b23-106">Method</span></span>|<span data-ttu-id="12b23-107">설명</span><span class="sxs-lookup"><span data-stu-id="12b23-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12b23-108">ICorDebugRemote::CreateProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="12b23-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="12b23-109">관리 디버깅을 위해 원격 컴퓨터에 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12b23-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="12b23-110">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="12b23-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="12b23-111">디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="12b23-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12b23-112">주의</span><span class="sxs-lookup"><span data-stu-id="12b23-112">Remarks</span></span>  
 <span data-ttu-id="12b23-113">현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상의 디버깅에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12b23-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b23-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12b23-114">Requirements</span></span>  
 <span data-ttu-id="12b23-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12b23-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b23-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12b23-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12b23-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12b23-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12b23-118">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="12b23-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b23-119">참조</span><span class="sxs-lookup"><span data-stu-id="12b23-119">See also</span></span>

- [<span data-ttu-id="12b23-120">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12b23-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="12b23-121">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12b23-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="12b23-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12b23-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
