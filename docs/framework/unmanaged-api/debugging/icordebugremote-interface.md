---
description: '자세히 알아보기: ICorDebugRemote 인터페이스'
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
ms.openlocfilehash: 4c9d92800c68155216a077180ea0b613c67423dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790674"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="668b8-103">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="668b8-103">ICorDebugRemote Interface</span></span>

<span data-ttu-id="668b8-104">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="668b8-104">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668b8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="668b8-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="668b8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="668b8-106">Methods</span></span>  
  
|<span data-ttu-id="668b8-107">메서드</span><span class="sxs-lookup"><span data-stu-id="668b8-107">Method</span></span>|<span data-ttu-id="668b8-108">설명</span><span class="sxs-lookup"><span data-stu-id="668b8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="668b8-109">ICorDebugRemote::CreateProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="668b8-109">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="668b8-110">관리 디버깅을 위해 원격 컴퓨터에 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="668b8-110">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="668b8-111">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="668b8-111">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="668b8-112">디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="668b8-112">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="668b8-113">설명</span><span class="sxs-lookup"><span data-stu-id="668b8-113">Remarks</span></span>  

 <span data-ttu-id="668b8-114">현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상의 디버깅에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="668b8-114">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668b8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="668b8-115">Requirements</span></span>  

 <span data-ttu-id="668b8-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="668b8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668b8-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="668b8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="668b8-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="668b8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="668b8-119">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="668b8-119">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668b8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="668b8-120">See also</span></span>

- [<span data-ttu-id="668b8-121">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="668b8-121">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="668b8-122">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="668b8-122">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="668b8-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="668b8-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
