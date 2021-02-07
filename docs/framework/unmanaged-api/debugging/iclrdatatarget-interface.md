---
description: '자세히 알아보기: ICLRDataTarget 인터페이스'
title: ICLRDataTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: f24760f638705a1bde7e055069cbc3a18a0896fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738223"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="c6d59-103">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d59-103">ICLRDataTarget Interface</span></span>

<span data-ttu-id="c6d59-104">CLR (공용 언어 런타임)의 대상 항목과 상호 작용 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-104">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6d59-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-105">Methods</span></span>  
  
|<span data-ttu-id="c6d59-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-106">Method</span></span>|<span data-ttu-id="c6d59-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6d59-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6d59-108">GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-108">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="c6d59-109">현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-109">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="c6d59-110">GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-110">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="c6d59-111">지정 된 이미지에 대 한 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-111">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="c6d59-112">GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-112">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="c6d59-113">대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-113">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="c6d59-114">GetPointerSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-114">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="c6d59-115">현재 대상에 대 한 포인터의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-115">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="c6d59-116">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-116">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="c6d59-117">지정 된 식별자를 가진 스레드의 컨텍스트에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-117">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="c6d59-118">GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-118">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="c6d59-119">지정 된 스레드에 대 한 지정 된 인덱스의 TLS (스레드 로컬 저장소) 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-119">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="c6d59-120">ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-120">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="c6d59-121">지정 된 가상 메모리 주소에서 지정 된 버퍼로 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-121">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="c6d59-122">Request 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-122">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="c6d59-123">구현에 정의 된 대로 작업을 요청 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-123">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="c6d59-124">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-124">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="c6d59-125">대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-125">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="c6d59-126">SetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-126">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="c6d59-127">대상 프로세스에서 지정 된 스레드의 TLS (스레드 로컬 저장소)에 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-127">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="c6d59-128">WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d59-128">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="c6d59-129">지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-129">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d59-130">설명</span><span class="sxs-lookup"><span data-stu-id="c6d59-130">Remarks</span></span>  

 <span data-ttu-id="c6d59-131">API 클라이언트 (즉, 디버거)는 특정 대상 항목에 대해 적절 하 게이 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-131">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="c6d59-132">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c6d59-132">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d59-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6d59-133">Requirements</span></span>  

 <span data-ttu-id="c6d59-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6d59-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d59-135">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c6d59-135">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c6d59-136">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d59-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d59-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d59-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d59-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6d59-138">See also</span></span>

- [<span data-ttu-id="c6d59-139">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d59-139">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="c6d59-140">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d59-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
