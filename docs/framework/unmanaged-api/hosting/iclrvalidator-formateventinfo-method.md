---
title: ICLRValidator::FormatEventInfo 메서드
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40a60bb79c4b1e250ec2d363816d9837c6b51c91
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474204"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="b4fa0-102">ICLRValidator::FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b4fa0-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="b4fa0-103">지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fa0-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4fa0-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4fa0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4fa0-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="b4fa0-106">[in] 유효성 검사 오류 처리기로 전달 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="b4fa0-107">[in] `VEContext` 유효성 검사 오류에 대 한 컨텍스트 정보를 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="b4fa0-108">[out에서] 친숙 한 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="b4fa0-109">[in] 오류 메시지의 최대 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="b4fa0-110">[in] 메시지에 사용할 추가 매개 변수는 안전 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4fa0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b4fa0-111">Return Value</span></span>  
  
|<span data-ttu-id="b4fa0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4fa0-112">HRESULT</span></span>|<span data-ttu-id="b4fa0-113">설명</span><span class="sxs-lookup"><span data-stu-id="b4fa0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4fa0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4fa0-114">S_OK</span></span>|<span data-ttu-id="b4fa0-115">`FormatEventInfo` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="b4fa0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4fa0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4fa0-117">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4fa0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4fa0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4fa0-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-119">The call timed out.</span></span>|  
|<span data-ttu-id="b4fa0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4fa0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4fa0-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4fa0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4fa0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4fa0-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4fa0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4fa0-124">E_FAIL</span></span>|<span data-ttu-id="b4fa0-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4fa0-126">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4fa0-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4fa0-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4fa0-128">Requirements</span></span>  
 <span data-ttu-id="b4fa0-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4fa0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fa0-130">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="b4fa0-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b4fa0-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b4fa0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4fa0-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fa0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fa0-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4fa0-133">See also</span></span>
- [<span data-ttu-id="b4fa0-134">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4fa0-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="b4fa0-135">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4fa0-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
