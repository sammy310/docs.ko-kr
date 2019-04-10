---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154182"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="7c94a-102">CorValidatorModuleType 열거형</span><span class="sxs-lookup"><span data-stu-id="7c94a-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="7c94a-103">모듈의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c94a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c94a-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="7c94a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7c94a-105">Members</span></span>  
  
|<span data-ttu-id="7c94a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7c94a-106">Member</span></span>|<span data-ttu-id="7c94a-107">설명</span><span class="sxs-lookup"><span data-stu-id="7c94a-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="7c94a-108">모듈에는 잘못 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="7c94a-109">최소값을 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="7c94a-110">모듈에는 pe (이식 가능) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="7c94a-111">모듈에는.obj 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="7c94a-112">모듈은 편집 및 계속 디버거 세션을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="7c94a-113">모듈은 증분 방식으로 빌드된입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="7c94a-114">최대값을 `CorValidatorModuleType` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="7c94a-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c94a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c94a-115">Requirements</span></span>  
 <span data-ttu-id="7c94a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c94a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c94a-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c94a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c94a-118">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7c94a-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c94a-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7c94a-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c94a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c94a-120">See also</span></span>

- [<span data-ttu-id="7c94a-121">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7c94a-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
