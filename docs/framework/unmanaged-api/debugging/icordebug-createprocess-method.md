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
ms.openlocfilehash: b9ae2b36bff9b4a6c048a8de99fa7d09350b1401
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859713"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="7610b-102">ICorDebug::CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="7610b-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="7610b-103">디버거를 제어할 때 프로세스 및 해당 기본 스레드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7610b-104">구문</span><span class="sxs-lookup"><span data-stu-id="7610b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="7610b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7610b-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="7610b-106">진행 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="7610b-107">모듈은 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="7610b-108">진행 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="7610b-109">응용 프로그램 이름 (예: "SomeApp")은 첫 번째 인수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="7610b-110">진행 프로세스에 대 한 `SECURITY_ATTRIBUTES` 보안 설명자를 지정 하는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="7610b-111">가 `lpProcessAttributes` null 이면 프로세스에서 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="7610b-112">진행 프로세스의 주 스레드에 `SECURITY_ATTRIBUTES` 대 한 보안 설명자를 지정 하는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="7610b-113">가 `lpThreadAttributes` null 이면 스레드는 기본 보안 설명자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="7610b-114">진행 `true` 호출 프로세스의 각 상속 가능한 핸들이 시작 된 프로세스에서 상속 되거나 `false` 핸들이 상속 되지 않음을 나타내려면로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="7610b-115">상속 된 핸들에는 원래 핸들과 동일한 값 및 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="7610b-116">진행 시작 된 프로세스의 동작 및 우선 순위 클래스를 제어 하는 [Win32 프로세스 생성 플래그](/windows/win32/procthread/process-creation-flags) 의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="7610b-117">진행 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="7610b-118">진행 프로세스의 현재 디렉터리에 대 한 전체 경로를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="7610b-119">이 매개 변수가 null 이면 새 프로세스는 호출 프로세스와 동일한 현재 드라이브 및 디렉터리를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="7610b-120">진행 시작 된 프로세스에 `STARTUPINFOW` 대 한 주 창의 창 스테이션, 바탕 화면, 표준 핸들 및 모양을 지정 하는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="7610b-121">진행 시작할 프로세스에 대 `PROCESS_INFORMATION` 한 식별 정보를 지정 하는 Win32 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="7610b-122">진행 디버깅 옵션을 지정 하는 CorDebugCreateProcessFlags 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7610b-123">제한이 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7610b-124">설명</span><span class="sxs-lookup"><span data-stu-id="7610b-124">Remarks</span></span>  
 <span data-ttu-id="7610b-125">이 메서드의 매개 변수는 Win32 `CreateProcess` 메서드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="7610b-126">관리 되지 않는 혼합 모드 디버깅을 사용 하도록 `dwCreationFlags` 설정 하려면을 DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="7610b-127">관리 되는 디버깅만 사용 하려면 이러한 플래그를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7610b-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="7610b-128">디버거 및 디버깅할 프로세스 (연결 된 프로세스)가 단일 콘솔을 공유 하 고 interop 디버깅이 사용 되는 경우 연결 된 프로세스에서 콘솔 잠금을 유지 하 고 디버그 이벤트에서 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="7610b-129">그러면 디버거가 콘솔 사용 시도를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="7610b-130">이 문제를 방지 하려면 `dwCreationFlags` 매개 변수에서 CREATE_NEW_CONSOLE 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="7610b-131">IA-64 기반 및 AMD64 기반 플랫폼과 같은 Win9x 및 비 x86 플랫폼에서는 Interop 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7610b-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7610b-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7610b-132">Requirements</span></span>  
 <span data-ttu-id="7610b-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7610b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7610b-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7610b-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7610b-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7610b-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7610b-136">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7610b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7610b-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7610b-137">See also</span></span>

- [<span data-ttu-id="7610b-138">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7610b-138">ICorDebug Interface</span></span>](icordebug-interface.md)
