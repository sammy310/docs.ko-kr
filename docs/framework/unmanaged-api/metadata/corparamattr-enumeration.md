---
title: CorParamAttr 열거형
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f62b082db11a5f0bb930e33cb47acef76e7a04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092060"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="54b0b-102">CorParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="54b0b-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="54b0b-103">메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b0b-104">구문</span><span class="sxs-lookup"><span data-stu-id="54b0b-104">Syntax</span></span>  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="54b0b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="54b0b-105">Members</span></span>  
  
|<span data-ttu-id="54b0b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="54b0b-106">Member</span></span>|<span data-ttu-id="54b0b-107">설명</span><span class="sxs-lookup"><span data-stu-id="54b0b-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="54b0b-108">매개 변수를 메서드 호출으로 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="54b0b-109">매개 변수가 전달 되도록 메서드에서 반환을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="54b0b-110">매개 변수가 선택 사항임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="54b0b-111">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="54b0b-112">매개 변수 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="54b0b-113">매개 변수 마샬링 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="54b0b-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54b0b-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54b0b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54b0b-115">Requirements</span></span>  
 <span data-ttu-id="54b0b-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="54b0b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b0b-117">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="54b0b-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="54b0b-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="54b0b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54b0b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="54b0b-119">See also</span></span>

- [<span data-ttu-id="54b0b-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="54b0b-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
