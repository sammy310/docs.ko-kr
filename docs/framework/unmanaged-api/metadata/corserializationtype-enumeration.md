---
description: '자세히 알아보기: CorSerializationType 열거형'
title: CorSerializationType 열거형
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
ms.openlocfilehash: 86df23bf03037d329a3138798725058f1d24a450
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707386"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="c836c-103">CorSerializationType 열거형</span><span class="sxs-lookup"><span data-stu-id="c836c-103">CorSerializationType Enumeration</span></span>

<span data-ttu-id="c836c-104">공용 언어 런타임에 의해 개체가 serialize 되는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-104">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c836c-105">구문</span><span class="sxs-lookup"><span data-stu-id="c836c-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="c836c-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c836c-106">Members</span></span>  
  
|<span data-ttu-id="c836c-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c836c-107">Member</span></span>|<span data-ttu-id="c836c-108">설명</span><span class="sxs-lookup"><span data-stu-id="c836c-108">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="c836c-109">개체의 Serialization이 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-109">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="c836c-110">개체는 부울 형식으로 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-110">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="c836c-111">개체는 문자 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-111">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="c836c-112">개체는 부호 있는 1 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-112">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="c836c-113">개체는 부호 없는 1 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-113">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="c836c-114">개체는 부호 있는 2 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-114">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="c836c-115">개체는 부호 없는 2 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-115">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="c836c-116">개체는 부호 있는 4 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-116">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="c836c-117">개체는 부호 없는 4 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-117">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="c836c-118">개체는 부호 있는 8 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-118">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="c836c-119">개체는 부호 없는 8 바이트 정수로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-119">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="c836c-120">개체가 4 바이트 부동 소수점으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-120">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="c836c-121">개체가 8 바이트 부동 소수점으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-121">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="c836c-122">개체는 System.string 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-122">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="c836c-123">개체는 0이 아닌 1 차원 배열로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-123">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="c836c-124">개체가 제네릭 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-124">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="c836c-125">개체가 태그가 지정 된 개체로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-125">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="c836c-126">개체가 필드로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-126">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="c836c-127">개체는 속성으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-127">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="c836c-128">개체가 열거형으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c836c-128">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c836c-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c836c-129">Requirements</span></span>  

 <span data-ttu-id="c836c-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c836c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c836c-131">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="c836c-131">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c836c-132">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c836c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c836c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c836c-133">See also</span></span>

- [<span data-ttu-id="c836c-134">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c836c-134">Metadata Enumerations</span></span>](metadata-enumerations.md)
