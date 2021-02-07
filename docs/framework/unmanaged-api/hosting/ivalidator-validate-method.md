---
description: '자세히 알아보기: IValidator:: Validate 메서드'
title: IValidator::Validate 메서드
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 6df70274a788b949686fe2509b525c5a8b04089c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680020"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="63b0b-103">IValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="63b0b-103">IValidator::Validate Method</span></span>

<span data-ttu-id="63b0b-104">지정 된 PE (이식 가능한 실행 파일) 또는 MSIL (Microsoft 중간 언어) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-104">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b0b-105">구문</span><span class="sxs-lookup"><span data-stu-id="63b0b-105">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63b0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63b0b-106">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="63b0b-107">진행 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-107">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="63b0b-108">진행 파일이 로드 되는 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-108">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="63b0b-109">진행 수행 해야 하는 유효성 검사를 나타내는 [ValidatorFlags](validatorflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-109">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="63b0b-110">진행 유효성 검사를 종료 하기 전에 허용 되는 최대 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-110">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="63b0b-111">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-111">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="63b0b-112">진행 유효성을 검사할 파일의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-112">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="63b0b-113">진행 파일이 저장 되는 메모리 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-113">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="63b0b-114">진행 유효성을 검사할 파일의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-114">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63b0b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63b0b-115">Requirements</span></span>  

 <span data-ttu-id="63b0b-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63b0b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63b0b-117">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="63b0b-117">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="63b0b-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63b0b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63b0b-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b0b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
