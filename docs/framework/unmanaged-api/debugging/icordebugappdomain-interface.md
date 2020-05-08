---
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
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895167"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="0ee8b-102">ICorDebugAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ee8b-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="0ee8b-103">애플리케이션 도메인 디버깅에 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="0ee8b-104">이 인터페이스는 ICorDebugController의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ee8b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-105">Methods</span></span>  
  
|<span data-ttu-id="0ee8b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-106">Method</span></span>|<span data-ttu-id="0ee8b-107">설명</span><span class="sxs-lookup"><span data-stu-id="0ee8b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ee8b-108">Attach 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="0ee8b-109">응용 프로그램 도메인에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-110">EnumerateAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="0ee8b-111">응용 프로그램 도메인의 어셈블리에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-112">EnumerateBreakpoints 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="0ee8b-113">응용 프로그램 도메인의 모든 활성 중단점에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-114">EnumerateSteppers 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="0ee8b-115">응용 프로그램 도메인의 모든 활성 steppers에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-116">GetId 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="0ee8b-117">응용 프로그램 도메인의 고유 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-118">GetModuleFromMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="0ee8b-119">지정 된 메타 데이터 인터페이스를 사용 하 여 ICorDebugModule 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="0ee8b-120">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="0ee8b-121">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-122">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="0ee8b-123">CLR (공용 언어 런타임) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-124">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="0ee8b-125">응용 프로그램 도메인을 포함 하는 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="0ee8b-126">IsAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="0ee8b-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="0ee8b-127">디버거가 응용 프로그램 도메인에 연결 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ee8b-128">설명</span><span class="sxs-lookup"><span data-stu-id="0ee8b-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ee8b-129">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee8b-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ee8b-130">Requirements</span></span>  
 <span data-ttu-id="0ee8b-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee8b-132">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ee8b-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ee8b-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ee8b-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ee8b-134">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee8b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee8b-135">참조</span><span class="sxs-lookup"><span data-stu-id="0ee8b-135">See also</span></span>

- [<span data-ttu-id="0ee8b-136">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ee8b-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
