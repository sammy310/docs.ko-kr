---
title: ICorDebug::CreateProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 795392bc50d4b7c5eeb82b98230a52156f273f15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187371"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="338d0-102">ICorDebug::CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="338d0-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="338d0-103">디버거의 제어 기본 스레드 및 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="338d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="338d0-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="338d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="338d0-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="338d0-106">[in] 시작된 프로세스에서 실행 될 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="338d0-107">모듈 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="338d0-108">[in] 시작된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="338d0-109">응용 프로그램 이름 (예: "SomeApp.exe")는 첫 번째 인수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="338d0-110">[in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스에 대 한 보안 설명자를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="338d0-111">경우 `lpProcessAttributes` 가 null 인 프로세스는 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="338d0-112">[in] Win32에 대 한 포인터 `SECURITY_ATTRIBUTES` 프로세스의 주 스레드에 대 한 보안 설명자를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="338d0-113">경우 `lpThreadAttributes` 가 null 이면 스레드는 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="338d0-114">[in] 로 `true` 호출 프로세스에 상속할 수 있는 각 핸들 시작된 프로세스를 통해 상속 되었음을 나타내기 위해 또는 `false` 핸들이 상속 되지 않습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="338d0-115">상속 된 핸들에는 원래 핸들을 동일한 값 및 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="338d0-116">[in] 비트 조합 합니다 [Win32 프로세스 생성 플래그가](https://go.microsoft.com/fwlink/?linkid=69981) 우선 순위 클래스 및 시작된 프로세스의 동작을 제어 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-116">[in] A bitwise combination of the [Win32 Process Creation Flags](https://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="338d0-117">[in] 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="338d0-118">[in] 프로세스에 대 한 현재 디렉터리에 전체 경로 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="338d0-119">이 매개 변수가 null 이면 새 프로세스 호출 프로세스와 같은 현재 드라이브 및 디렉터리 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="338d0-120">[in] Win32에 대 한 포인터 `STARTUPINFOW` 윈도우 스테이션, 데스크톱, 표준 핸들 및 시작된 프로세스에 대 한 주 창의 모양을 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="338d0-121">[in] Win32에 대 한 포인터 `PROCESS_INFORMATION` 시작 될 프로세스에 대 한 식별 정보를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="338d0-122">[in] 디버깅 옵션을 지정 하는 CorDebugCreateProcessFlags 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="338d0-123">[out] 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="338d0-124">설명</span><span class="sxs-lookup"><span data-stu-id="338d0-124">Remarks</span></span>  
 <span data-ttu-id="338d0-125">이 메서드의 매개 변수는 Win32의 것과 동일 `CreateProcess` 메서드.</span><span class="sxs-lookup"><span data-stu-id="338d0-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="338d0-126">관리 되지 않는 혼합 모드 디버깅을 사용 하려면 `dwCreationFlags` DEBUG_PROCESS를 &#124; DEBUG_ONLY_THIS_PROCESS 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="338d0-127">관리 되는 디버깅만 사용 하려는 경우에 이러한 플래그를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="338d0-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="338d0-128">디버거 및 프로세스를 디버그 (연결 된 프로세스) 하는 경우 단일 콘솔 인 공유 하는 경우 사용 되는 interop 디버깅, 콘솔 잠금을 보유 하 고 디버그 이벤트에서 중지 하는 연결 된 프로세스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="338d0-129">디버거는 다음 콘솔을 사용 하려는 모든 시도 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="338d0-130">이 문제를 방지 하려면에서 CREATE_NEW_CONSOLE 플래그를 설정 합니다 `dwCreationFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="338d0-131">Interop 디버깅 IA-64 기반 및 AMD64 기반 플랫폼 등 Win9x 및 x86이 아닌 플랫폼에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="338d0-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="338d0-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="338d0-132">Requirements</span></span>  
 <span data-ttu-id="338d0-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="338d0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="338d0-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="338d0-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="338d0-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="338d0-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="338d0-136">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="338d0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338d0-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="338d0-137">See also</span></span>

- [<span data-ttu-id="338d0-138">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="338d0-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
