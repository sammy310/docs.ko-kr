---
description: '자세히 알아보기: ICorDebugAppDomain 인터페이스'
title: ICorDebugAppDomain 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 5f1ac20a7376a741da2e34de74c810c0f45e8293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754201"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="13d79-103">ICorDebugAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13d79-103">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="13d79-104">애플리케이션 도메인 디버깅에 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-104">Provides methods for debugging application domains.</span></span> <span data-ttu-id="13d79-105">이 인터페이스는 ICorDebugController의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-105">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13d79-106">메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-106">Methods</span></span>  
  
|<span data-ttu-id="13d79-107">메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-107">Method</span></span>|<span data-ttu-id="13d79-108">설명</span><span class="sxs-lookup"><span data-stu-id="13d79-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13d79-109">Attach 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-109">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="13d79-110">응용 프로그램 도메인에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-110">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="13d79-111">EnumerateAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-111">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="13d79-112">응용 프로그램 도메인의 어셈블리에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-112">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="13d79-113">EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-113">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="13d79-114">응용 프로그램 도메인의 모든 활성 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-114">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="13d79-115">EnumerateSteppers 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-115">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="13d79-116">응용 프로그램 도메인의 모든 활성 steppers에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-116">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="13d79-117">GetId 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-117">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="13d79-118">응용 프로그램 도메인의 고유 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-118">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="13d79-119">GetModuleFromMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-119">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="13d79-120">지정 된 메타 데이터 인터페이스를 사용 하 여 ICorDebugModule 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-120">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="13d79-121">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-121">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="13d79-122">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-122">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="13d79-123">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-123">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="13d79-124">CLR (공용 언어 런타임) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-124">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="13d79-125">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-125">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="13d79-126">응용 프로그램 도메인을 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-126">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="13d79-127">IsAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="13d79-127">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="13d79-128">디버거가 응용 프로그램 도메인에 연결 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-128">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13d79-129">설명</span><span class="sxs-lookup"><span data-stu-id="13d79-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13d79-130">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13d79-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d79-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13d79-131">Requirements</span></span>  

 <span data-ttu-id="13d79-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13d79-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d79-133">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13d79-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13d79-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13d79-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13d79-135">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d79-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d79-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13d79-136">See also</span></span>

- [<span data-ttu-id="13d79-137">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13d79-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
