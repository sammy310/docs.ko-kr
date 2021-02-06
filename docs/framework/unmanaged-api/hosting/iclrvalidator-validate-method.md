---
description: '자세히 알아보기: ICLRValidator:: Validate 메서드'
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
ms.openlocfilehash: a188315d44021fc8bf40be9bb9aecac436351467
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636744"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="44511-103">ICLRValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="44511-103">ICLRValidator::Validate Method</span></span>

<span data-ttu-id="44511-104">지정 된 파일에서 PE (이식 가능한 실행) 또는 MSIL (Microsoft 중간 언어)의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="44511-104">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44511-105">구문</span><span class="sxs-lookup"><span data-stu-id="44511-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="44511-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44511-106">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="44511-107">진행 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-107">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="44511-108">진행 현재의 식별자입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="44511-108">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="44511-109">진행 수행 해야 하는 유효성 검사의 종류를 나타내는 [ValidatorFlags](validatorflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-109">[in] A combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="44511-110">진행 유효성 검사를 종료 하기 전에 허용 되는 최대 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-110">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="44511-111">진행 사용 되지 않는.</span><span class="sxs-lookup"><span data-stu-id="44511-111">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="44511-112">진행 유효성을 검사할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-112">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="44511-113">진행 파일 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-113">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="44511-114">진행 유효성을 검사할 파일의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="44511-114">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44511-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="44511-115">Return Value</span></span>  
  
|<span data-ttu-id="44511-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44511-116">HRESULT</span></span>|<span data-ttu-id="44511-117">설명</span><span class="sxs-lookup"><span data-stu-id="44511-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44511-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="44511-118">S_OK</span></span>|<span data-ttu-id="44511-119">`Validate` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-119">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="44511-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="44511-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="44511-121">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="44511-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="44511-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="44511-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-123">The call timed out.</span></span>|  
|<span data-ttu-id="44511-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="44511-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="44511-125">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="44511-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="44511-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="44511-127">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="44511-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="44511-128">E_FAIL</span></span>|<span data-ttu-id="44511-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="44511-130">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44511-130">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="44511-131">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44511-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44511-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44511-132">Requirements</span></span>  

 <span data-ttu-id="44511-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44511-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44511-134">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="44511-134">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="44511-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44511-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44511-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44511-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44511-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44511-137">See also</span></span>

- [<span data-ttu-id="44511-138">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44511-138">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
