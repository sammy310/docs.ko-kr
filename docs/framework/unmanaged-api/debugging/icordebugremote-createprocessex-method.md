---
description: '자세히 알아보기: ICorDebugRemote:: CreateProcessEx 메서드'
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
ms.openlocfilehash: cd27400f5c9f348621fb66b3b7730cf15d397151
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794730"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="3f2ee-103">ICorDebugRemote::CreateProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="3f2ee-103">ICorDebugRemote::CreateProcessEx Method</span></span>

<span data-ttu-id="3f2ee-104">디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-104">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f2ee-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f2ee-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3f2ee-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f2ee-106">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="3f2ee-107">진행 [ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-107">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="3f2ee-108">프로세스가 시작 되는 원격 컴퓨터를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-108">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="3f2ee-109">진행 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-109">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="3f2ee-110">모듈은 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-110">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="3f2ee-111">진행 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-111">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="3f2ee-112">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-112">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="3f2ee-113">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-113">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="3f2ee-114">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-114">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="3f2ee-115">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-115">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="3f2ee-116">진행 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-116">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="3f2ee-117">진행 프로세스의 현재 디렉터리에 대 한 전체 경로를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-117">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="3f2ee-118">이 매개 변수가 null 이면 새 프로세스는 호출 프로세스와 동일한 현재 드라이브 및 디렉터리를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-118">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="3f2ee-119">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-119">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="3f2ee-120">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-120">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="3f2ee-121">진행 원격 디버깅에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-121">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="3f2ee-122">제한이 프로세스를 나타내는 "ICorDebugProcess Interface" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-122">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f2ee-123">Return Value</span><span class="sxs-lookup"><span data-stu-id="3f2ee-123">Return Value</span></span>  

 <span data-ttu-id="3f2ee-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f2ee-124">S_OK</span></span>  
 <span data-ttu-id="3f2ee-125">원격 컴퓨터에서 프로세스를 시작 하 고 디버깅을 위해 "ICorDebugProcess Interface"를 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-125">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="3f2ee-126">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="3f2ee-126">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3f2ee-127">원격 컴퓨터에서 프로세스를 시작 하 고 디버깅을 위해 "ICorDebugProcess Interface"를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-127">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f2ee-128">설명</span><span class="sxs-lookup"><span data-stu-id="3f2ee-128">Remarks</span></span>  

 <span data-ttu-id="3f2ee-129">Silverlight에서는 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-129">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f2ee-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f2ee-130">Requirements</span></span>  

 <span data-ttu-id="3f2ee-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f2ee-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f2ee-132">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="3f2ee-132">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="3f2ee-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f2ee-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f2ee-134">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3f2ee-134">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2ee-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f2ee-135">See also</span></span>

- [<span data-ttu-id="3f2ee-136">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f2ee-136">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="3f2ee-137">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f2ee-137">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="3f2ee-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f2ee-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
