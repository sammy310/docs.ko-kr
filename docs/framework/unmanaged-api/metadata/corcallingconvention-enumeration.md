---
title: CorCallingConvention 열거형
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046113"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="4406b-102">CorCallingConvention 열거형</span><span class="sxs-lookup"><span data-stu-id="4406b-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="4406b-103">관리 코드에서 수행된 호출 규칙의 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4406b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4406b-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="4406b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4406b-105">Members</span></span>  
  
|<span data-ttu-id="4406b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4406b-106">Member</span></span>|<span data-ttu-id="4406b-107">설명</span><span class="sxs-lookup"><span data-stu-id="4406b-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="4406b-108">기본 호출 규칙을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="4406b-109">메서드는 가변 개수의 매개 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="4406b-110">필드에 호출 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="4406b-111">로컬 메서드 호출 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="4406b-112">속성 호출 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="4406b-113">관리 되지 않는 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="4406b-114">제네릭 메서드 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="4406b-115">64 비트 PInvoke 호출에 가변 개수의 매개 변수를 사용 하는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="4406b-116">잘못 된 4 비트 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="4406b-117">호출 규칙 하위 4 비트에서 설명한 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="4406b-118">최상위 비트 설명 나타냅니다는 `this` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="4406b-119">나타내는 `this` 매개 변수는 서명에서 명시적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="4406b-120">명시적 개수의 형식 인수를 사용 하 여 제네릭 메서드 시그니처를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="4406b-121">이 일반 매개 변수 개수를 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="4406b-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4406b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4406b-122">Requirements</span></span>  
 <span data-ttu-id="4406b-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4406b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4406b-124">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4406b-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4406b-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4406b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4406b-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="4406b-126">See also</span></span>

- [<span data-ttu-id="4406b-127">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4406b-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
