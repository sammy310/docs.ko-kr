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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129250"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="5dc83-102">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5dc83-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="5dc83-103">호스트에서 오류 보고를 위해 사용자 지정 스택 덤프를 구성할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5dc83-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5dc83-104">Methods</span></span>  
  
|<span data-ttu-id="5dc83-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5dc83-105">Method</span></span>|<span data-ttu-id="5dc83-106">설명</span><span class="sxs-lookup"><span data-stu-id="5dc83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5dc83-107">BeginCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="5dc83-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="5dc83-108">오류 보고에 대 한 사용자 지정 스택 덤프의 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="5dc83-109">EndCustomDump 메서드</span><span class="sxs-lookup"><span data-stu-id="5dc83-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="5dc83-110">`BeginCustomDump`에 대 한 이전 호출에 의해 설정 된 사용자 지정 스택 덤프 구성을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="5dc83-111">GetBucketParametersForCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="5dc83-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="5dc83-112">호출 스레드의 현재 예외에 대 한 Watson 버킷을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dc83-113">주의</span><span class="sxs-lookup"><span data-stu-id="5dc83-113">Remarks</span></span>  
 <span data-ttu-id="5dc83-114">`BeginCustomDump` 메서드는 사용자 지정 스택 덤프 구성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="5dc83-115">`EndCustomDump` 메서드는 사용자 지정 스택 덤프 구성을 지우고 연결 된 상태를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="5dc83-116">사용자 지정 덤프가 완료 된 후이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5dc83-117">`EndCustomDump` 호출 하지 못하면 메모리 누수가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc83-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5dc83-118">Requirements</span></span>  
 <span data-ttu-id="5dc83-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5dc83-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc83-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5dc83-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5dc83-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dc83-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc83-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc83-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc83-123">참조</span><span class="sxs-lookup"><span data-stu-id="5dc83-123">See also</span></span>

- [<span data-ttu-id="5dc83-124">ECustomDumpItemKind 열거형</span><span class="sxs-lookup"><span data-stu-id="5dc83-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="5dc83-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5dc83-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
