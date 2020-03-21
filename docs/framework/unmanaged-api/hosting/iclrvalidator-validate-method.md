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
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178057"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="9520f-102">ICLRValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="9520f-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="9520f-103">지정된 파일에서 이식 가능한 실행 파일(PE) 또는 Microsoft 중간 언어(MSIL)의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9520f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9520f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9520f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9520f-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="9520f-106">【인】 유효성 검사 `IVEHandler` 오류를 처리하는 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="9520f-107">【인】 현재 <xref:System.AppDomain>의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="9520f-108">【인】 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 값의 조합으로 수행해야 하는 유효성 검사 의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="9520f-109">【인】 유효성 검사를 종료하기 전에 허용할 최대 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="9520f-110">【인】 하지 않는.</span><span class="sxs-lookup"><span data-stu-id="9520f-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9520f-111">【인】 유효성을 검사할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="9520f-112">【인】 파일 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="9520f-113">【인】 유효성을 검사할 파일의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9520f-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="9520f-114">Return Value</span></span>  
  
|<span data-ttu-id="9520f-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9520f-115">HRESULT</span></span>|<span data-ttu-id="9520f-116">Description</span><span class="sxs-lookup"><span data-stu-id="9520f-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9520f-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9520f-117">S_OK</span></span>|<span data-ttu-id="9520f-118">`Validate`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="9520f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9520f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9520f-120">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9520f-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9520f-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9520f-122">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-122">The call timed out.</span></span>|  
|<span data-ttu-id="9520f-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9520f-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9520f-124">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9520f-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9520f-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9520f-126">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9520f-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9520f-127">E_FAIL</span></span>|<span data-ttu-id="9520f-128">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9520f-129">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9520f-130">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9520f-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9520f-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9520f-131">Requirements</span></span>  
 <span data-ttu-id="9520f-132">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9520f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9520f-133">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="9520f-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9520f-134">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9520f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9520f-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9520f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9520f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9520f-136">See also</span></span>

- [<span data-ttu-id="9520f-137">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9520f-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
