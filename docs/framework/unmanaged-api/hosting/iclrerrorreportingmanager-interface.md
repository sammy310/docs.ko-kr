---
title: ICLRErrorReportingManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966253"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="ee8cb-102">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee8cb-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="ee8cb-103">호스트에서 오류 보고를 위해 사용자 지정 스택 덤프를 구성할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee8cb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ee8cb-104">Methods</span></span>  
  
|<span data-ttu-id="ee8cb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ee8cb-105">Method</span></span>|<span data-ttu-id="ee8cb-106">Description</span><span class="sxs-lookup"><span data-stu-id="ee8cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee8cb-107">BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="ee8cb-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="ee8cb-108">오류 보고에 대 한 사용자 지정 스택 덤프의 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="ee8cb-109">EndCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="ee8cb-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="ee8cb-110">에 대 `BeginCustomDump`한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="ee8cb-111">GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="ee8cb-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="ee8cb-112">호출 스레드의 현재 예외에 대 한 Watson 버킷을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee8cb-113">설명</span><span class="sxs-lookup"><span data-stu-id="ee8cb-113">Remarks</span></span>  
 <span data-ttu-id="ee8cb-114">메서드 `BeginCustomDump` 는 사용자 지정 스택 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="ee8cb-115">메서드 `EndCustomDump` 는 사용자 지정 스택 덤프 구성을 지우고 연결 된 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="ee8cb-116">사용자 지정 덤프가 완료 된 후이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ee8cb-117">호출 `EndCustomDump` 하지 못하면 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee8cb-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee8cb-118">Requirements</span></span>  
 <span data-ttu-id="ee8cb-119">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee8cb-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ee8cb-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee8cb-121">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee8cb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee8cb-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee8cb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee8cb-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee8cb-123">See also</span></span>

- [<span data-ttu-id="ee8cb-124">ECustomDumpItemKind 열거형</span><span class="sxs-lookup"><span data-stu-id="ee8cb-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="ee8cb-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee8cb-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
