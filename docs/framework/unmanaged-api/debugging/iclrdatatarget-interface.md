---
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
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860570"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="4138c-102">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4138c-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="4138c-103">CLR (공용 언어 런타임)의 대상 항목과 상호 작용 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4138c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-104">Methods</span></span>  
  
|<span data-ttu-id="4138c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-105">Method</span></span>|<span data-ttu-id="4138c-106">Description</span><span class="sxs-lookup"><span data-stu-id="4138c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4138c-107">GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="4138c-108">현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="4138c-109">GetImageBase 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="4138c-110">지정 된 이미지에 대 한 기본 메모리 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="4138c-111">GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="4138c-112">대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="4138c-113">GetPointerSize 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="4138c-114">현재 대상에 대 한 포인터의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="4138c-115">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="4138c-116">지정 된 식별자를 가진 스레드의 컨텍스트에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="4138c-117">GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="4138c-118">지정 된 스레드에 대 한 지정 된 인덱스의 TLS (스레드 로컬 저장소) 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="4138c-119">ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="4138c-120">지정 된 가상 메모리 주소에서 지정 된 버퍼로 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="4138c-121">Request 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="4138c-122">구현에 정의 된 대로 작업을 요청 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="4138c-123">SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="4138c-124">대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="4138c-125">SetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="4138c-126">대상 프로세스에서 지정 된 스레드의 TLS (스레드 로컬 저장소)에 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="4138c-127">WriteVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="4138c-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="4138c-128">지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4138c-129">설명</span><span class="sxs-lookup"><span data-stu-id="4138c-129">Remarks</span></span>  
 <span data-ttu-id="4138c-130">API 클라이언트 (즉, 디버거)는 특정 대상 항목에 대해 적절 하 게이 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="4138c-131">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4138c-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4138c-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4138c-132">Requirements</span></span>  
 <span data-ttu-id="4138c-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4138c-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4138c-134">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="4138c-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4138c-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4138c-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4138c-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4138c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4138c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4138c-137">See also</span></span>

- [<span data-ttu-id="4138c-138">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4138c-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="4138c-139">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4138c-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
