---
description: '자세히 알아보기: CorValidatorModuleType 열거형'
title: CorValidatorModuleType 열거형
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 13792c461660ddd8cfd530f5b34d642d806cdea4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707250"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="8720f-103">CorValidatorModuleType 열거형</span><span class="sxs-lookup"><span data-stu-id="8720f-103">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="8720f-104">모듈의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-104">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8720f-105">구문</span><span class="sxs-lookup"><span data-stu-id="8720f-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="8720f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8720f-106">Members</span></span>  
  
|<span data-ttu-id="8720f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8720f-107">Member</span></span>|<span data-ttu-id="8720f-108">설명</span><span class="sxs-lookup"><span data-stu-id="8720f-108">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="8720f-109">모듈의 형식이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-109">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="8720f-110">열거형의 최소값 `CorValidatorModuleType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-110">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="8720f-111">모듈은 PE (이식 가능한 실행) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-111">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="8720f-112">모듈은 .obj 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-112">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="8720f-113">이 모듈은 편집 하며 계속 하기 디버거 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-113">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="8720f-114">모듈은 증분 방식으로 작성 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-114">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="8720f-115">열거형의 최대값 `CorValidatorModuleType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-115">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8720f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8720f-116">Requirements</span></span>  

 <span data-ttu-id="8720f-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8720f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8720f-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8720f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8720f-119">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8720f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8720f-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8720f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8720f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8720f-121">See also</span></span>

- [<span data-ttu-id="8720f-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8720f-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
