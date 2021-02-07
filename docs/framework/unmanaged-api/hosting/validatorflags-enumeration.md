---
description: '자세히 알아보기: ValidatorFlags 열거형'
title: ValidatorFlags 열거형
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: 473b0eef2851126256e1ea6b6d2b82be32e03e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679123"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="8d299-103">ValidatorFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="8d299-103">ValidatorFlags Enumeration</span></span>

<span data-ttu-id="8d299-104">[ICLRValidator:: Validate](iclrvalidator-validate-method.md) 메서드에 대 한 호출에서 수행 해야 하는 유효성 검사의 형식을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-104">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d299-105">구문</span><span class="sxs-lookup"><span data-stu-id="8d299-105">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="8d299-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8d299-106">Members</span></span>  
  
|<span data-ttu-id="8d299-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8d299-107">Member</span></span>|<span data-ttu-id="8d299-108">설명</span><span class="sxs-lookup"><span data-stu-id="8d299-108">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="8d299-109">실행 파일의 MSIL (Microsoft 중간 언어)만 유효성을 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-109">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="8d299-110">실행 파일의 형식만 유효성을 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-110">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="8d299-111">모든 유효성 검사 유형을 수행 하 고 보고 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-111">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="8d299-112">실행 파일의 형식에 대 한 유효성을 검사 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-112">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="8d299-113">유효성 검사 오류 메시지에 유효성 검사 오류를 발생 시키는 소스 코드 줄을 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-113">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="8d299-114">.NET Framework 버전 2.0에서는이 필드 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d299-114">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d299-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d299-115">Requirements</span></span>  

 <span data-ttu-id="8d299-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d299-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d299-117">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="8d299-117">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="8d299-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d299-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d299-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d299-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d299-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d299-120">See also</span></span>

- [<span data-ttu-id="8d299-121">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d299-121">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="8d299-122">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="8d299-122">Hosting Enumerations</span></span>](hosting-enumerations.md)
