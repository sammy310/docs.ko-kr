---
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
ms.openlocfilehash: 92c430cdb8b46cf75dde9a8395ce713116dc05a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732864"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="0dc28-102">ValidatorFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="0dc28-102">ValidatorFlags Enumeration</span></span>

<span data-ttu-id="0dc28-103">[ICLRValidator:: Validate](iclrvalidator-validate-method.md) 메서드에 대 한 호출에서 수행 해야 하는 유효성 검사의 형식을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc28-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dc28-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0dc28-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0dc28-105">Members</span></span>  
  
|<span data-ttu-id="0dc28-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0dc28-106">Member</span></span>|<span data-ttu-id="0dc28-107">설명</span><span class="sxs-lookup"><span data-stu-id="0dc28-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="0dc28-108">실행 파일의 MSIL (Microsoft 중간 언어)만 유효성을 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="0dc28-109">실행 파일의 형식만 유효성을 검사 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="0dc28-110">모든 유효성 검사 유형을 수행 하 고 보고 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="0dc28-111">실행 파일의 형식에 대 한 유효성을 검사 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="0dc28-112">유효성 검사 오류 메시지에 유효성 검사 오류를 발생 시키는 소스 코드 줄을 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="0dc28-113">.NET Framework 버전 2.0에서는이 필드 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc28-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dc28-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dc28-114">Requirements</span></span>  

 <span data-ttu-id="0dc28-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dc28-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dc28-116">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="0dc28-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="0dc28-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0dc28-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0dc28-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dc28-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc28-119">참조</span><span class="sxs-lookup"><span data-stu-id="0dc28-119">See also</span></span>

- [<span data-ttu-id="0dc28-120">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0dc28-120">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="0dc28-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="0dc28-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
