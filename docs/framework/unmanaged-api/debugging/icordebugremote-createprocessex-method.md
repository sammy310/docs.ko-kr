---
title: ICorDebugRemote::CreateProcessEx 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05384af8201fae8cf81650d38c99a5c44e6bd16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744779"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="8754f-102">ICorDebugRemote::CreateProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8754f-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="8754f-103">디버거에서 원격 컴퓨터의 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8754f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8754f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8754f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8754f-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="8754f-106">[in] 에 대 한 포인터를 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="8754f-107">프로세스를 시작할 수는 원격 컴퓨터를 확인 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="8754f-108">[in] 시작된 프로세스에서 실행 될 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="8754f-109">모듈 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="8754f-110">[in] 시작된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="8754f-111">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="8754f-112">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="8754f-113">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="8754f-114">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="8754f-115">[in] 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="8754f-116">[in] 프로세스에 대 한 현재 디렉터리에 전체 경로 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="8754f-117">이 매개 변수가 null 이면 새 프로세스 호출 프로세스와 같은 현재 드라이브 및 디렉터리 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="8754f-118">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="8754f-119">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="8754f-120">[in] 원격 디버깅을 위해 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="8754f-121">[out] 프로세스를 나타내는 "ICorDebugProcess 인터페이스" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8754f-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="8754f-122">Return Value</span></span>  
 <span data-ttu-id="8754f-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="8754f-123">S_OK</span></span>  
 <span data-ttu-id="8754f-124">디버깅에 대 한 원격 컴퓨터에 반환 된 "ICorDebugProcess 인터페이스" 프로세스를 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="8754f-125">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="8754f-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8754f-126">원격 컴퓨터의 프로세스를 시작 하 고 디버깅에 대 한 "ICorDebugProcess 인터페이스"를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8754f-127">설명</span><span class="sxs-lookup"><span data-stu-id="8754f-127">Remarks</span></span>  
 <span data-ttu-id="8754f-128">Silverlight에는 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8754f-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8754f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8754f-129">Requirements</span></span>  
 <span data-ttu-id="8754f-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8754f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8754f-131">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="8754f-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="8754f-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8754f-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8754f-133">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8754f-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8754f-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="8754f-134">See also</span></span>

- [<span data-ttu-id="8754f-135">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8754f-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="8754f-136">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8754f-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="8754f-137">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8754f-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
