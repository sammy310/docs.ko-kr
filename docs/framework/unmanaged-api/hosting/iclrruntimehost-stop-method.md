---
title: ICLRRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166974"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="1698f-102">ICLRRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="1698f-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="1698f-103">CLR (공용 언어 런타임)에서 코드의 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1698f-104">이 메서드는 없는 호스트 리소스를 해제, 응용 프로그램 도메인 언로드 또는 스레드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="1698f-105">이러한 리소스를 해제 하는 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1698f-106">구문</span><span class="sxs-lookup"><span data-stu-id="1698f-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1698f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1698f-107">Return Value</span></span>  
  
|<span data-ttu-id="1698f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1698f-108">HRESULT</span></span>|<span data-ttu-id="1698f-109">설명</span><span class="sxs-lookup"><span data-stu-id="1698f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1698f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1698f-110">S_OK</span></span>|`Stop` <span data-ttu-id="1698f-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-111">returned successfully.</span></span>|  
|<span data-ttu-id="1698f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1698f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1698f-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1698f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1698f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1698f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-115">The call timed out.</span></span>|  
|<span data-ttu-id="1698f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1698f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1698f-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1698f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1698f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1698f-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1698f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1698f-120">E_FAIL</span></span>|<span data-ttu-id="1698f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1698f-122">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1698f-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1698f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1698f-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1698f-124">Requirements</span></span>  
 <span data-ttu-id="1698f-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1698f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1698f-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1698f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1698f-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1698f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1698f-128">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1698f-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1698f-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="1698f-129">See also</span></span>

- [<span data-ttu-id="1698f-130">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1698f-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
