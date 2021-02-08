---
description: '자세히 알아보기: ICLRDataTarget3 인터페이스'
title: ICLRDataTarget3 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: deea609298563e60897f9bedab9fb1e175dc7b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794791"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="2131e-103">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2131e-103">ICLRDataTarget3 Interface</span></span>

<span data-ttu-id="2131e-104">예외 정보에 대 한 액세스를 제공 하는 [ICLRDataTarget2](iclrdatatarget2-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-104">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2131e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2131e-105">Methods</span></span>  
  
|<span data-ttu-id="2131e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2131e-106">Method</span></span>|<span data-ttu-id="2131e-107">설명</span><span class="sxs-lookup"><span data-stu-id="2131e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2131e-108">GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="2131e-108">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="2131e-109">공용 언어 런타임(CLR)에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 예외 레코드 검색을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-109">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="2131e-110">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="2131e-110">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="2131e-111">CLR에 의해 호출되는 데이터 액세스는 대상 프로세스와 연관된 컨텍스트 레코드 검색을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-111">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="2131e-112">GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="2131e-112">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="2131e-113">CLR 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-113">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2131e-114">설명</span><span class="sxs-lookup"><span data-stu-id="2131e-114">Remarks</span></span>  

 <span data-ttu-id="2131e-115">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-115">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="2131e-116">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-116">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="2131e-117">대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2131e-117">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2131e-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2131e-118">Requirements</span></span>  

 <span data-ttu-id="2131e-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2131e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2131e-120">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="2131e-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2131e-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2131e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2131e-122">**.NET Framework 버전:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2131e-122">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2131e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2131e-123">See also</span></span>

- [<span data-ttu-id="2131e-124">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2131e-124">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="2131e-125">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2131e-125">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="2131e-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2131e-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
