---
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
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123277"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="3041c-102">IValidator::Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="3041c-102">IValidator::Validate Method</span></span>
<span data-ttu-id="3041c-103">지정 된 PE (이식 가능한 실행 파일) 또는 MSIL (Microsoft 중간 언어) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3041c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3041c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3041c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3041c-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="3041c-106">진행 유효성 검사 오류를 처리 하는 `IVEHandler` 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="3041c-107">진행 파일이 로드 되는 응용 프로그램 도메인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="3041c-108">진행 수행 해야 하는 유효성 검사를 나타내는 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="3041c-109">진행 유효성 검사를 종료 하기 전에 허용 되는 최대 오류 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="3041c-110">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="3041c-111">진행 유효성을 검사할 파일의 이름을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="3041c-112">진행 파일이 저장 되는 메모리 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="3041c-113">진행 유효성을 검사할 파일의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3041c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3041c-114">Requirements</span></span>  
 <span data-ttu-id="3041c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3041c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3041c-116">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="3041c-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="3041c-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3041c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3041c-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3041c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
