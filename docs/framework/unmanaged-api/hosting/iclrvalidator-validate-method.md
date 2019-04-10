---
title: ICLRValidator::Validate 메서드
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 559c265c70c199e64782ba185d4925d293d6a778
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158693"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="2b436-102">ICLRValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="2b436-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="2b436-103">Pe (이식 가능) 또는 MSIL (Microsoft intermediate language) 지정된 된 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b436-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b436-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
## <a name="parameters"></a><span data-ttu-id="2b436-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b436-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="2b436-106">[in] 에 대 한 포인터는 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="2b436-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="2b436-107">[in] 현재 식별자 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="2b436-108">[in] 조합을 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 수행 해야 하는 유효성 검사의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="2b436-109">[in] 유효성 검사를 종료 하기 전까지 허용 오류의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="2b436-110">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="2b436-111">[in] 유효성을 검사할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="2b436-112">[in] 파일 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="2b436-113">[in] 유효성을 검사할 파일의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b436-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="2b436-114">Return Value</span></span>  
  
|<span data-ttu-id="2b436-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b436-115">HRESULT</span></span>|<span data-ttu-id="2b436-116">설명</span><span class="sxs-lookup"><span data-stu-id="2b436-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b436-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b436-117">S_OK</span></span>|`Validate` <span data-ttu-id="2b436-118">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-118">returned successfully.</span></span>|  
|<span data-ttu-id="2b436-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b436-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b436-120">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b436-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b436-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b436-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-122">The call timed out.</span></span>|  
|<span data-ttu-id="2b436-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b436-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b436-124">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b436-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b436-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b436-126">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b436-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b436-127">E_FAIL</span></span>|<span data-ttu-id="2b436-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b436-129">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b436-130">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b436-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b436-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b436-131">Requirements</span></span>  
 <span data-ttu-id="2b436-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b436-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b436-133">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="2b436-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="2b436-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2b436-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2b436-135">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2b436-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b436-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b436-136">See also</span></span>

- [<span data-ttu-id="2b436-137">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b436-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
