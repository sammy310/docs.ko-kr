---
description: '자세히 알아보기: ICorDebugProcess2 인터페이스'
title: ICorDebugProcess2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 47e94ee8ee4f45e365fa9efe888cb706f8bb1dfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746596"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="3d178-103">ICorDebugProcess2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d178-103">ICorDebugProcess2 Interface</span></span>

<span data-ttu-id="3d178-104">관리 코드를 실행 하는 프로세스를 나타내는 ICorDebugProcess 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-104">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d178-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-105">Methods</span></span>  
  
|<span data-ttu-id="3d178-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-106">Method</span></span>|<span data-ttu-id="3d178-107">설명</span><span class="sxs-lookup"><span data-stu-id="3d178-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d178-108">ClearUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-108">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="3d178-109">에 대 한 이전 호출에 의해 설정 된 지정 된 오프셋에서 중단점을 제거 `ICorDebugProcess2::SetUnmanagedBreakpoint` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-109">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="3d178-110">GetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-110">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="3d178-111">이에서 참조 하는 프로세스에 이미지를 로드 하기 위해 CLR (공용 언어 런타임)에 대해 설정 해야 하는 플래그를 가져옵니다 `ICorDebugProcess2` .</span><span class="sxs-lookup"><span data-stu-id="3d178-111">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="3d178-112">GetReferenceValueFromGCHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-112">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="3d178-113">가비지 수집 핸들이 있는 지정 된 관리 되는 개체에 대 한 참조 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-113">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="3d178-114">GetThreadForTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-114">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="3d178-115">지정 된 식별자를 가진 태스크가 실행 중인 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-115">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="3d178-116">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-116">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="3d178-117">디버깅 중인 프로세스가 실행 되는 CLR의 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-117">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="3d178-118">SetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-118">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="3d178-119">JIT (just-in-time) 컴파일러가 디버깅 중인 프로세스에 이미지를 로드 하는 데 필요한 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-119">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="3d178-120">SetUnmanagedBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="3d178-120">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="3d178-121">지정 된 네이티브 이미지 오프셋에서 관리 되지 않는 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-121">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d178-122">설명</span><span class="sxs-lookup"><span data-stu-id="3d178-122">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d178-123">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d178-123">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d178-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d178-124">Requirements</span></span>  

 <span data-ttu-id="3d178-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d178-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d178-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d178-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d178-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d178-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d178-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d178-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d178-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d178-129">See also</span></span>

- [<span data-ttu-id="3d178-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d178-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
