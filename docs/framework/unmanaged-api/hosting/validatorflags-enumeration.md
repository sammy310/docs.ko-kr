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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5f38231eb6a5911527c21ee3304fc77cfcf8e90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776524"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="c2833-102">ValidatorFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="c2833-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="c2833-103">에 대 한 호출에서 수행 해야 하는 유효성 검사의 유형을 나타내는 값을 포함 합니다 [iclrvalidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c2833-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2833-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2833-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="c2833-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c2833-105">Members</span></span>  
  
|<span data-ttu-id="c2833-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c2833-106">Member</span></span>|<span data-ttu-id="c2833-107">Description</span><span class="sxs-lookup"><span data-stu-id="c2833-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="c2833-108">만 MSIL (Microsoft intermediate language) 실행 파일의 유효성을 검사 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="c2833-109">실행 파일의 형식에만 검사할지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="c2833-110">모든 유형의 유효성 검사 수행 및 보고를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="c2833-111">실행 파일의 형식을 확인 하지 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="c2833-112">지정 된 유효성 검사 오류 메시지 유효성 검사 오류가 발생 하는 소스 코드 줄을 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="c2833-113">필드 값이.NET Framework 버전 2.0에서에서 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2833-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2833-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2833-114">Requirements</span></span>  
 <span data-ttu-id="c2833-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2833-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2833-116">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="c2833-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="c2833-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2833-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2833-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2833-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2833-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2833-119">See also</span></span>

- [<span data-ttu-id="c2833-120">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2833-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="c2833-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c2833-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
