---
description: '다음에 대 한 자세한 정보: CorParamAttr 열거형'
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
ms.openlocfilehash: c07569d3fb92b20a7985dbfeb2205af727866051
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784290"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="e8640-103">CorParamAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="e8640-103">CorParamAttr Enumeration</span></span>

<span data-ttu-id="e8640-104">메서드 매개 변수의 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-104">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8640-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8640-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="e8640-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e8640-106">Members</span></span>  
  
|<span data-ttu-id="e8640-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e8640-107">Member</span></span>|<span data-ttu-id="e8640-108">설명</span><span class="sxs-lookup"><span data-stu-id="e8640-108">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="e8640-109">매개 변수가 메서드 호출에 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-109">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="e8640-110">매개 변수가 메서드 반환에서 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-110">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="e8640-111">매개 변수를 선택적 요소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-111">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="e8640-112">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-112">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="e8640-113">매개 변수가 기본값을 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-113">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="e8640-114">매개 변수에 마샬링 정보를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-114">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="e8640-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8640-115">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8640-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8640-116">Requirements</span></span>  

 <span data-ttu-id="e8640-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8640-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8640-118">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="e8640-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e8640-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8640-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8640-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8640-120">See also</span></span>

- [<span data-ttu-id="e8640-121">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e8640-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
